pipeline {
    agent any

    tools {
        jdk 'JDK17'
        maven 'maven'
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/mohamed-iaazi/devops.git', branch: 'master'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
