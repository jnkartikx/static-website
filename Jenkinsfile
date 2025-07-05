pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID = credentials('AWS_ACCESS_KEY_ID') 
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
    }
    stages {
        stage('Checkout Code') {
            steps {
                git credentialsId: 'your-credentials-id', url: 'https://github.com/jnkartikx/static-website.git'
            }
        }
        stage('Deploy to S3') {
            steps {
                bat '''
                    aws s3 sync . s3://myprojectbucket-152 --region eu-north-1 --delete
                '''
            }
        }
    }
}
