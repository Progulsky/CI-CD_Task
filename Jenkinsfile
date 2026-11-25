pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('CI: Lint & Validate') {
            steps {
                script {
                    if (!fileExists('index.php') || !fileExists('docker-compose.yml')) {
                        error('Не знайдено index.php або docker-compose.yml!')
                    }
                }
                echo 'PHP 8.2 syntax check: OK (simulated)'
                echo 'Docker Compose config validation: OK (simulated)'
            }
        }

        stage('CD: Deploy') {
            steps {
                echo 'Deploy LAMP stack to server: OK (simulated)'
            }
        }
    }
}
