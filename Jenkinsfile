pipeline {
    agent any 

     environment {
        AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
        AWS_SECRET_ACCESS_KEY = credentials('jenkins-aws-secret-access-key')
    }      

   stages {
        stage('Upload to S3') {
                    archiveArtifacts 'Desktop/*.html'
                    sh 'aws configure set region us-west-2'
                    sh 'aws s3 cp Desktop/index.html s3://mystaticweb2513.com/index.html'
                    bat 'aws configure set region us-west-2'
                    bat 'aws s3 cp Desktop/index.html s3://mystaticweb2513.com/index.html'
                }
            }
        }
    

