pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/mustaqim12345/devops-project-repo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t java-app .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'ansible-playbook ansible/deploy.yml'
            }
        }

    }
}

