pipeline {
    agent any
    environment {
        DIRECTORY_PATH         = 'var/jenkins_home/workspace/sit-753-task-5-1'
        TESTING_ENVIRONMENT    = 'test-env'
        PRODUCTION_ENVIRONMENT = 'daniel-garcia-vargas'
    }
    stages {
        stage('Build') {
            steps {
                echo "Task: Fetch the source code from ${env.DIRECTORY_PATH}, compile the code, and generate necessary artifacts."
                echo "Tool: npm for Node.js."
            }
        }
        stage('Test') { 
            steps {
                echo "Task: Run unit tests and integration tests."
                echo "Tools: Jest for unit tests in Node.js."
            }
        }
        stage('Code Quality Check') {
            steps {
                echo "Task: Perform code quality analysis."
                echo "Tool: SonarQube."
            }
        }
        stage('Security Scan') {
            steps {
                echo "Task: Perform a security scan on the code to identify vulnerabilities."
                echo "Tool: OWASP Dependency Check."
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Task: Deploy the application to the testing environment (${env.TESTING_ENVIRONMENT})."
                echo "Tool: AWS EKS (Elastic Kubernetes Service) for containerized applications."
            }
        }
        stage('Approval') {
            steps {
                echo "Task: Simulate manual approval process."
                echo "Tool: Pause the pipeline for a manual approval (e.g., sleep or input step)."
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Task: Run integration tests in the staging environment."
                echo "Tool: Selenium for integration testing."
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Task: Deploy the application to the production environment (${env.PRODUCTION_ENVIRONMENT})."
                echo "Tool: AWS EKS (Elastic Kubernetes Service) for containerized applications."
            }
        }
    }
}
