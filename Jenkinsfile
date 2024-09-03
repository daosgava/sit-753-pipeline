pipeline {
    agent any
    environment {
        DIRECTORY_PATH         = 'var/jenkins_home/workspace/sit-753-task-5-1'
        TESTING_ENVIRONMENT    = 'test-env'
        PRODUCTION_ENVIRONMENT = 'daniel-oswaldo-garcia-vargas'
        EMAIL_RECIPIENT        = 'daosgava.garcia@gmail.com'
    }
    stages {
        stage('Build') {
            steps {
                echo "Task: Fetch the source code from ${env.DIRECTORY_PATH}, compile the code, and generate necessary artifacts."
                echo "Tool: npm for Node.js. - change"
            }
        }
        stage('Test') { 
            steps {
                echo "Task: Run unit tests and integration tests."
                echo "Tools: Jest for unit tests in Node.js."
                sh 'echo "Test log content: Simulated test logs." > test.text'
            }
            post {
                success {
                    archiveArtifacts artifacts: 'test.text', onlyIfSuccessful: true
                    emailext attachLog: true, attachmentsPattern: 'test.text',
                    body: "The Test stage has ${currentBuild.currentResult}. Please check the attached logs for details.",
                    subject: "Jenkins: Test Stage - ${currentBuild.currentResult}",
                    to: "${env.EMAIL_RECIPIENT}"
                }
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
                sh 'echo "Security Scan log content: Simulated security scan logs." > security-scan.text'
            }
            post {
                success {
                    archiveArtifacts artifacts: 'security-scan.text', onlyIfSuccessful: true
                    emailext attachLog: true, attachmentsPattern: 'security-scan.text',
                    body: "The Security Scan stage has ${currentBuild.currentResult}. Please check the attached logs for details.",
                    to: "${env.EMAIL_RECIPIENT}",
                    subject: "Jenkins: Security Scan Stage - ${currentBuild.currentResult}"
                }
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
