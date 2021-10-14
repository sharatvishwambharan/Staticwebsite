pipeline {
    agent any 

     environment {
        AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
        AWS_SECRET_ACCESS_KEY = credentials('jenkins-aws-secret-access-key')
    }      

   stages{
      stage('Upload to S3'){
          steps{
              script{
                  dir(''){
                      pwd();
                      withAWS(region:'us-west-2')
                      def identity=awsIdentity();
                      s3Upload(bucket: "mystaticweb2513.com", workingDir:'',includePathPattern:'**/*');
                  }
              };
                  }
      }
   }
}
