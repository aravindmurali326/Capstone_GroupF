pipeline {
    agent any
    stages {
        stage('deploy') {
            steps {
              sh "aws configure set region $AWS_DEFAULT_REGION" 
              sh "aws configure set aws_access_key_id $AWS_ACCESS_KEY_ID"  
              sh "aws configure set aws_secret_access_key $AWS_SECRET_ACCESS_KEY"
              sh "rm -rf *"  
              sh 'cp -r /var/lib/jenkins/workspace/Testgitclone/* .'
              sh 'pwd'  
              sh "ls -la "
              sh "aws s3 cp ./* s3://my-static-website-cbd3384 --recursive"
            }
        }
    }
}
