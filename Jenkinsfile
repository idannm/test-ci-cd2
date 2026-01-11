pipeline {
    agent {
        // דרישה: All pipeline stages must run on Docker agents
        docker { image 'python:3.9-slim' }
    }
    stages {
        stage('Build & Test') {
            steps {
                sh 'pip install -r requirements.txt'
                sh 'pytest' 
            }
        }
        stage('Build & Push to ECR') {
            steps {
                // כאן יבוא הקוד של בניית האימג' ודחיפה ל-ECR (CI Flow)
                echo 'Building and Pushing to ECR...'
            }
        }
        stage('Deploy to Prod') {
            when {
                // דרישה: רק ב-Merge למאסטר (CD Flow)
                branch 'main' 
            }
            steps {
                // פקודות ה-Deploy ל-EC2 של ה-Production
                echo 'Deploying to Production...'
            }
        }
    }
}
