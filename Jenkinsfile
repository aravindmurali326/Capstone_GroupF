pipeline {
    agent any
    stages {
        stage('Build from Github') {
            steps {
              echo "Pulling code from Github"
              sh "sleep 5"  
            }
        }
        stage('Test in Jenkins') {
            steps {
              echo "Test Looks good!!!"
              sh "sleep 3" 
            }
        }
        stage('deploy to S3') {
            steps {
              sh "sleep 3" 
              sh "aws configure set region $AWS_DEFAULT_REGION" 
              sh "aws configure set aws_access_key_id $AWS_ACCESS_KEY_ID"  
              sh "aws configure set aws_secret_access_key $AWS_SECRET_ACCESS_KEY"
              sh "rm -rf *"  
              sh 'cp -r /var/lib/jenkins/workspace/CI-Github-Jenkins/* .'
              sh 'pwd'  
              sh "ls -la "
              //sh "aws s3 cp ./* s3://my-static-website-cbd3384 --recursive"
              sh "aws s3 sync /var/lib/jenkins/workspace/CD-Jenkins-AWS-S3 s3://my-static-website-cbd3384"
              echo "All done"
            }
        }
    }
}
