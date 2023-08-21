pipeline {
    agent any
    stages {
        stage('Compile') {
            steps {
                script {
                    withMaven(maven: 'Maven 3.3.9', jdk: 'jdk8') {
                        sh 'mvn compile'
                    }
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    withMaven(maven: 'Maven 3.3.9', jdk: 'jdk8') {
                        sh 'mvn test'
                    }
                }
            }
        }
        stage('Package') {
            steps {
                script {
                    withMaven(maven: 'Maven 3.3.9', jdk: 'jdk8') {
                        sh 'mvn package'
                    }
                }
            }
        }
    }
}
