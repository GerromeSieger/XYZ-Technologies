pipeline {
    agent any
    tools {
        maven 'Maven 3.6.3'
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }        
        stage('Compile') {
            agent {
                label 'slave-node-1'
            }
            steps {
                sh 'mvn compile'
            }
        }
        stage('Test') {
            agent {
                label 'slave-node-1'
            }
            steps {
                sh 'mvn test'
            }
        }
        stage('Package') {
            agent {
                label 'slave-node-1'
            }            
            steps {
                sh 'mvn package'
            }
        }
    }
}
