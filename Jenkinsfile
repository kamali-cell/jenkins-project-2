pipeline {
    agent any
    stages {
        stage('Checkout Source Code') {
            steps {
                // Downloads your files from GitHub into Jenkins
                checkout scm
            }
        }
        stage('Generate Exam Report') {
            steps {
                // Runs the Python script to build the report
                bat 'python app.py'
            }
        }
        stage('Archive System Artifacts') {
            steps {
                // Saves the report.txt file onto your Jenkins dashboard
                archiveArtifacts artifacts: 'report.txt', fingerprint: true
            }
        }
    }
}
