pipeline {
    agent any 

     environment {
        AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
        AWS_SECRET_ACCESS_KEY = credentials('jenkins-aws-secret-access-key')
    }      

    stages {
     stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Publish') {
            steps {
                sh './mvnw package'
                // bat '.\mvnw package'
            }
            post {
                success {
                    archiveArtifacts 'Desktop/*.html'
                    sh 'aws configure set region us-west-2'
                    sh 'aws s3 cp Desktop/index.html s3://mystaticweb2513.com/index.html'
                    bat 'aws configure set region us-west-2'
                    bat 'aws s3 cp Desktop/index.html s3://mystaticweb2513.com/index.html'
                }
            }
        }
    }
}

  
