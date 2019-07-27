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
        stage ('deployment') {
			steps {
				sshagent(['centos']) {
					sh 'scp -o StrictHostKeyChecking=no target/*.war centos@34.204.183.34:/opt/tomcat/apache-tomcat/webapps/'
				}
			}
		
		}
		              
    }
}

