pipeline {
  agent any
  environment {
    BUCKET_NAME = 'myprojectbucket-152'
    REGION = 'eu-north-1'
  }
  stages {
    stage('Clone') {
      steps {
        git 'https://github.com/jnkartikx/static-website.git'
      }
    }
    stage('Deploy to S3') {
      steps {
        sh 'aws s3 sync . s3://$BUCKET_NAME --region $REGION --delete'
      }
    }
  }
}
