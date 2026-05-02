pipeline {
    agent any

    environment {
        // Define any environment variables here
        VERCEL_TOKEN = credentials('vercel-token') // Example of using Jenkins credentials  
    }
    stages {
        stage('Install') {
            steps {
                bat 'npm install' 
                // Add your build steps here
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // Add your test steps here
            }
        }
        stage('Build') {
            steps {
                bat 'npm run build'
                // Add your build steps here
            }
        }
        stage('Deploy') {
            steps {
                bat 'npx vercel --prod --yes --token $VERCEL_TOKEN'
                // Add your deploy steps here
            }
        }
    }   
}