pipeline {
    agent any

    tools {
        maven 'Maven-3.8.6' 
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/AmmarEzzedini/projetsession.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Déploiement de l\'application...'
                sh './deploy.sh'
            }
        }
    }
}