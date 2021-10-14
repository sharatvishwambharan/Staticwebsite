pipeline {
    agent any 

     environment {
        AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
        AWS_SECRET_ACCESS_KEY = credentials('jenkins-aws-secret-access-key')
    }      

   stages{
      stage('deploy to S3'){
          steps{
              sh 'aws s3 cp Desktop/index.html s3://mystaticweb2513.com'
              sh 'aws s3api put-object-acl --bucket mystaticweb2513.com --key ${secrets.AWS_ACCESS_KEY_ID, secrets.AWS_SECRET_ACCESS_KEY} --acl public-read'
              bat 'aws s3 cp Desktop/index.html s3://mystaticweb2513.com'
              bat 'aws s3api put-object-acl --bucket mystaticweb2513.com --key ${secrets.AWS_ACCESS_KEY_ID, secrets.AWS_SECRET_ACCESS_KEY} --acl public-read'
          }
      }
   }
}
