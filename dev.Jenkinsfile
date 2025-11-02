pipeline {
    agent any

    environment {
        GITHUB_REPO = 'https://github.com/manishk169/nginx.git'
        BRANCH_NAME = 'dev' // Branch to deploy from
    }

    stages {
        stage('Checkout Source Code') {
            steps {
                // Correct syntax for git step (no 'script' block needed)
                git branch: "${BRANCH_NAME}", url: "${GITHUB_REPO}"
            }
        }
        
        stage('Deploy Web Page') {
            steps {
                // Correct syntax for shell command with sudo
                sh 'sudo cp index.html /var/www/html/index.html'
            }
        }
        
        stage('Restart Nginx') {
            steps {
                // Correct syntax for shell command with sudo
                sh 'sudo systemctl restart nginx'
            }
        }
    }
}
