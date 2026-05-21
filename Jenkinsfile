pipeline {
    agent any

    stages {
        // Stage 1: Get the code from GitHub
        stage('Clone Repository') {
            steps {
                checkout scm
            }
        }

        // Stage 2: Install project packages
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        // Stage 3: Build the React app
        stage('Build Application') {
            steps {
                sh 'npm run build'
            }
        }

        // Stage 4: THIS IS WHERE YOU ADD YOUR DOCKER CODE
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t react-cicd-app:latest .'
            }
        }
    }
}