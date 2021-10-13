pipeline {
    agent any

stages{
      stage('deploy to S3'){
          steps{
              sh 'aws s3 cp public/index.html s3://<bucket-name>'
              sh 'aws s3api put-object-acl --bucket <bucket-name> --key index.html --acl public-read'
              sh 'aws s3 cp public/error.html s3://<bucket-name>'
              sh 'aws s3api put-object-acl --bucket <bucket-name> --key error.html --acl public-read'
          }
      }
  }
