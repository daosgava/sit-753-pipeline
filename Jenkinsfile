pipeline {
    agent { docker { image 'node:20.17.0-alpine3.20' } }
    environment {
        DIRECTORY_PATH         = 'var/jenkins_home/workspace/my-pipeline-project'
        TESTING_ENVIRONMENT    = 'test-env'
        PRODUCTION_ENVIRONMENT = 'daniel-garcia'
    }
    stages {
        stage('Build') {
            steps {
                echo "Fetch the source code from the directory path specified by the environment variable: ${env.DIRECTORY_PATH}"
                echo "Compile the code and generate any necessary artifacts"
            }
        }
        stage('Test') { 
            steps {
                echo "Unit tests"
                echo "Integration tests"
            }
        }
        stage('Code Quality Check') {
            steps {
                echo "Check the quality of the code"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploy the application to a testing environment specified by the environment variable: ${env.TESTING_ENVIRONMENT}"
            }
        }
        stage('Approval') {
            steps {
                echo "Simulating manual approval by pausing for 10 seconds"
                sleep time: 10, unit: 'SECONDS'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploy the code to the production environment specified by the environment variable: ${env.PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}