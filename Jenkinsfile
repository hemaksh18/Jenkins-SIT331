pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Building the code using maven..'
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests using Junit.'
                echo 'Running integration tests... selenium'
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo 'Running code analysis...using sonarQube'
            }
        }
        
        stage('Security Scan') {
            steps {
                echo 'Performing security scan using OWASP ZAP'
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying the application.'
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo 'Deploying the application to production server Amazon EC2'
            }
        }
    }
    post {
        success {
            emailext subject: "Pipeline '${currentBuild.fullDisplayName}' Successful",
                      body: 'The build was successful. Congratulations!',
                      to: 'hemaksh4791.be22@chitkara.edu.in',
                      attachLog: true
        }
        failure {
            emailext subject: "Pipeline '${currentBuild.fullDisplayName}' Failed",
                      body: 'The build has failed. Please investigate.',
                      to:'hemaksh4791.be22@chitkara.edu.in',
                      attachLog: true
        }
    }
}
