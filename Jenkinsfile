pipeline {
    agent any
stages{
      stage('deploy to S3'){
          steps{
              sh 'aws s3 cp Desktop/index.html s3://mystaticwebsite2513'
              sh 'aws s3api put-object-acl --bucket mystaticwebsite2513 --key c8a6ffed-9e3c-4cc1-b0b4-3a342ee92464 --acl public-read'
              sh 'aws s3 cp Desktop/error.html s3://mystaticwebsite2513'
              sh 'aws s3api put-object-acl --bucket mystaticwebsite2513 --key c8a6ffed-9e3c-4cc1-b0b4-3a342ee92464 --acl public-read'
          }
      }
  }
