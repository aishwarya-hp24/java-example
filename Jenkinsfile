pipeline {
    agent {
		label 'build'
	}
	stages {
		stage('checkout') {
				steps {
					git branch: 'main', credentialsId: 'github', url: 'https://github.com/aishwarya-hp24/java-example.git'
				}
			}

		stage('test') {
			steps {
				echo 'This is a test case and is taken care while building an artifact'
			}
		}

		stage('build') {
			steps {
				sh 'mvn clean package'
			}
		}

		stage('deploy') {
			steps {
				sh 'sudo cp target/*.war  /opt/tomcat/apache-tomcat-9.0.68/webapps'
			}
		}
	
	}
}
