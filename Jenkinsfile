pipeline {
    agent any
stages{
      stage('deploy to S3'){
          steps{
              sh 'aws s3 cp Desktop/index.html s3://mystaticwebsite2513 --region us-west-2'
              sh 'aws s3api put-object-acl --bucket mystaticwebsite2513 --key AKIA4M5QZU5EJFICSMR2 --acl public-read'
              sh 'aws s3 cp Desktop/error.html s3://mystaticwebsite2513 --region us-west-2'
              sh 'aws s3api put-object-acl --bucket mystaticwebsite2513 --key AKIA4M5QZU5EJFICSMR2 --acl public-read'
          }
      }
}
}
