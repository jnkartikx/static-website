pipeline {
    agent any

    environment {
        GIT_REPO_URL = 'https://github.com/jnkartikx/static-website.git'
    }

    stages {
        stage('Checkout from GitHub') {
            steps {
                git url: "${https://github.com/jnkartikx/static-website}", branch: 'master'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                // Add your build commands here
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add your test commands here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the project...'
                // Add your deployment commands here
            }
        }
    }
}
