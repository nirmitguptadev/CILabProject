pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps { checkout scm }
        }
        stage('Build & Test') {
            steps {
                bat "\"D:\\maven\\apache-maven-3.9.12\\bin\\mvn.cmd\" clean package"
            }
        }
        stage('Security Scan') {
            when { branch 'release*' }
            steps { echo "Security Scan for Release branch..." }
        }
        stage('Deploy') {
            when { branch 'main' }
            steps {
                echo "Deploying via script..."
                // Logic for main branch only
                bat "echo Build Successfully Packaged"
            }
        }
    }
    post {
        always {
            junit '**/target/surefire-reports/*.xml'
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
        }
    }
}
