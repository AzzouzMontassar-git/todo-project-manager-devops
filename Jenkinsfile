pipeline {
    agent any
    tools {
        jdk 'JDK17'
        maven 'Maven3'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/AzzouzMontassar-git/todo-project-manager-devops.git'
            }
        }
        stage('Build') {
            steps {
                bat 'mvnw.cmd clean package'
            }
        }
        stage('Test') {
            steps {
                bat 'mvnw.cmd test'
            }
        }
    }
    post {
        success { echo 'Build and tests successful!' }
        failure { echo 'Build or tests failed.' }
    }
}
