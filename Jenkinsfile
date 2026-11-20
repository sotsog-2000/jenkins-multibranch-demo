
pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo "Branch: ${env.BRANCH_NAME}"
                echo 'Checking out source code'
            }
        }

        stage('Build') {
            steps {
                echo "Building ${env.BRANCH_NAME}"
                sh 'echo Build successful'
            }
        }

        stage('Test') {
            steps {
                echo "Testing ${env.BRANCH_NAME}"
                sh 'echo Test successful'
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }

            steps {
                echo 'Deploying production application'
            }
        }
    }

    post {
        success {
            echo "Pipeline successful: ${env.BRANCH_NAME}"
        }

        failure {
            echo "Pipeline failed: ${env.BRANCH_NAME}"
        }
    }
}
