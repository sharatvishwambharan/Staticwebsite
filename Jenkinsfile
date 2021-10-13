pipeline {
  agent any
  stages {
    stage('Deploy to s3') {
      when {
        branch 'main'
      }
      steps {
        slackSend channel: "#<channel>", message: "Deployment Starting: ${env.JOB_NAME}, build number ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)"
        echo 'Deploying to RDG AWS s3 bucket.'
        withAWS(region:'<AWS Region: like us-west-2>', credentials:'RDG AWS') {
          s3Delete(bucket: 'mystaticwebsite2513', path:'**/*')
          s3Upload(bucket: 'mystaticwebsite2513', includePathPattern:'**/*')
        }
      }
    }
  }
  post {
    success {
      slackSend channel: "#<channel>", color: "good", message: "Deployment Complete: ${env.JOB_NAME}, build number ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)"
    }
    failure {
      slackSend channel: "#<channel>", color: "danger", message: "Deployment Failed: ${env.JOB_NAME}, build number ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)"
    }
    // always {
    //   slackSend ...
    // }
  }
}
