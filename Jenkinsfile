pipeline {
    agent any
    stages {
        stage ('Compile Stage') {
            steps {
                withMaven(maven : 'Maven_3.3.9') {
                    sh 'mvn clean compile'
                }
            }
        }
        stage ('Testing Stage') {
            steps {
                withMaven(maven : 'Maven_3.3.9') {
                    sh 'mvn test'
                }
            }
        }
        stage ('Install stage') {
            steps {
                withMaven(maven : 'Maven_3.3.9') {
                    sh 'mvn clean install'
                }
            }
        }
    }
}

