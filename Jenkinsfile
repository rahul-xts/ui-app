pipeline {
    agent any
    environment {
        PHP_DIR = "/var/www/html/php-frontend"
    }
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'master', url: 'https://github.com/rahul-xts/ui-app.git'
            }
        }
        stage('Deploy PHP') {
            steps {
                sh 'cp -r * $PHP_DIR'
            }
        }
        stage('Restart Apache') {
            steps {
                sh 'sudo systemctl restart apache2'
            }
        }
    }
}
