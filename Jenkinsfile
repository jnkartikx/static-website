pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git credentialsId: 'AWS_CREDENTIALS', url: 'https://github.com/jnkartikx/static-website.git'
            }
        }

        stage('Deploy to S3') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'AWS_CREDENTIALS', usernameVariable: 'AWS_ACCESS_KEY_ID', passwordVariable: 'AWS_SECRET_ACCESS_KEY')]) {
                    bat '''
                        set AWS_ACCESS_KEY_ID=%AWS_ACCESS_KEY_ID%
                        set AWS_SECRET_ACCESS_KEY=%AWS_SECRET_ACCESS_KEY%
                        aws s3 sync . s3://myprojectbucket-152 --region eu-north-1 --delete
                    '''
                }
            }
        }
    }
}
