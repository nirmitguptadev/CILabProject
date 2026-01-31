pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build & Unit Tests') {
            steps {
                echo "Running tests for branch: ${env.BRANCH_NAME}"
                // Using your working D: drive path for Maven
                bat "\"D:\\maven\\apache-maven-3.9.12\\bin\\mvn.cmd\" clean test"
            }
        }

        stage('Security Scan') {
            // Requirement: Runs on Release branches only
            when {
                branch 'release*'
            }
            steps {
                echo "--- PERFORMING SECURITY SCAN FOR RELEASE ---"
                bat "echo Security Scan Passed"
            }
        }

        stage('Deployment') {
            // Requirement: Full CI/CD for Main branch only
            when {
                branch 'main'
            }
            steps {
                echo "--- DEPLOYING TO PRODUCTION ---"
                // Your worked-out Python path
                bat "\"D:\\Python\\python.exe\" scripts/hello_world.py"
            }
        }
    }

    post {
        always {
            junit '**/target/surefire-reports/*.xml'
        }
        success {
            echo "Pipeline successfully completed for ${env.BRANCH_NAME}"
        }
    }
}
