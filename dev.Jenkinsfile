pipeline {
    agent any
    
    environment {
        GITHUB_REPO = 'https://github.com/manishk169/nginx.git'
        BRANCH = 'main'  // Branch to deploy from
    }

    stages {
        stage('Checkout') {
            steps {
                script 
                    git branch: "${BRANCH}", url: "${GITHUB_REPO}"
                }
            }
        }
        
        stage('Deploy Web Page') {
            steps {
                script {
                    sh 'sudo cp index.html /var/www/html/index.html'
                }
            }
        }
        
        stage('Restart Nginx') {
            steps {
                script {
                    sh 'sudo systemctl restart nginx'
                }	
            }
        }
    }
