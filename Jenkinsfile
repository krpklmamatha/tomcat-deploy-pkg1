pipeline {
	agent {label 'linux-node'}
	stages {
		stage('---clean---'){
			tools {
				maven 'maven3.9.6'
			}
			steps {
				sh 'mvn --version'
				sh "mvn clean"
			}
		}
		stage('---test---') {
			tools {
				maven 'maven3.9.0'
			}
			steps {
				sh 'mvn --version'
				sh "mvn test"
			}
		}
		stage('---package---'){
			tools {
				maven 'maven3.8.6'
			}
			
			steps {
				sh 'mvn --version'
				sh "mvn package"
			}
		}
	}
	post {
		success {
			echo 'job was built successfully - update sent by github webhook '
		}
		failure {
			echo 'job was not build..it was failed - update sent by github webhook '
		}
	}
}
