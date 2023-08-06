pipeline {
    agent any

    stages {
        stage('Install HTTP Server') {
            steps {
                sh 'sudo dnf install -y nginx'
            }
        }
        stage('Check HTTP Server Logs') {
            steps {
                sh 'if grep -E "HTTP/[0-9]+\\.[0-9]+\\" (4[0-9][0-9]|5[0-9][0-9])" /var/log/nginx/access.log; then echo "Errors found in the log file."; else echo "No errors found in the log file."; fi'
            }
        }
    }
}
