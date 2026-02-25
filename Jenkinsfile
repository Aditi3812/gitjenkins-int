pipeline {
    agent any 
    stages {
        stage('Fetch Code') {
            steps {
                echo 'Pulling the latest code from GitHub'
                checkout scm
            }
        }
        stage('Quality Check') {
            steps {
                echo 'Checking if Python is accessible...'
                // Using the path we found earlier
                bat '"C:\\Users\\user\\AppData\\Local\\Programs\\Python\\Python313\\python.exe" --version'
            }
        }

        stage('Run Script') {
            steps {
                echo 'Executing the main Python script...'
                bat '"C:\\Users\\user\\AppData\\Local\\Programs\\Python\\Python313\\python.exe" first.py'
            }
        }
    }
    post {
        always {
            echo 'Cleaning up the workspace.'
        }
        success {
            echo 'Build was successful! High fives all around.'
        }
        failure {
            echo 'Build failed. Check the logs above!'
        }
    }
}