pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout your code from version control
                git 'https://github.com/Rudraksh2003/Django-React-NotesApp.git'
            }
        }
        stage('Setup Environment') {
            steps {
                // Create and activate virtual environment
                script {
                    if (isUnix()) {
                        sh 'python3 -m venv env'
                        sh 'source env/bin/activate'
                    } else {
                        bat 'python -m venv env'
                        bat 'env\\Scripts\\activate'
                    }
                }
                // Install dependencies
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Run Tests') {
            steps {
                // Run your Django tests
                sh 'python manage.py test'
            }
        }
        stage('Build and Deploy') {
            steps {
                // Build and deploy your Django app
                sh 'python manage.py migrate' // Apply migrations
                sh 'python manage.py collectstatic --noinput' // Collect static files
                
                // Run server in the background
                sh 'nohup python manage.py runserver &'
                
                // Optional: Run some smoke tests or health checks to ensure server is up
                // Example: sh 'sleep 10 && curl http://localhost:8000/health'
            }
        }
    }
    
    post {
        always {
            // Clean up environment
            script {
                if (isUnix()) {
                    sh 'kill $(lsof -t -i:8000)'
                    sh 'deactivate'
                } else {
                    bat 'taskkill /F /PID $(netstat -aon | findstr :8000 | findstr LISTENING | awk "{print $5}")'
                    bat 'env\\Scripts\\deactivate'
                }
            }
        }
    }
}
