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

        stage('CI') {
            steps {
                sh 'docker run --rm -v "$WORKSPACE":/app -w /app php:8.2-apache find . -name "*.php" -exec php -l {} +'
                sh 'docker compose config -q'
            }
        }

        stage('CD') {
            steps {
                sh 'echo "Docker compose up simulated"'
            }
        }
    }
}