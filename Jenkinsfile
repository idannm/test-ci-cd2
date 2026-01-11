pipeline {
    agent
        // דרישה: שימוש ב-Docker Agen
        // דרישה: All pipeline stages must run on Docker agents
     origin/main
        docker { image 'python:3.9-slim' }
    }
    stages {
        stage('Build & Test') {
            steps {
                sh 'pip install -r requirements.txt'
                sh 'pytest' // הרצת הבדיקות של המחשבון
            }
        }

        stage('Build and Push Image') {
            steps {
                script {
                    // כאן בונים את ה-Docker Image של המחשבון
                    // דרישה: שימוש ב-ECR וסודות מ-Jenkins Credentials
                    echo "Building and Pushing to ECR..."
                }
            }
        }

        stage('Deploy to Prod') {
            when {
                // דרישה: רק ב-Merge ל-Master (CD Flow)
                branch 'master' 
            }
            steps {
                echo "Deploying to Production EC2..."
                // כאן תכתוב את פקודת ה-SSH לשרת ה-Production
=======
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
>>>>>>> origin/main
            }
        }
    }
}
