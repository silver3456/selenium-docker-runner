pipeline {
	agent any  
	stages {
		stage("Pull Latest Image") {
			steps {
				sh "docker pull silver3456/selenium-docker"
			}
		}
	}
	stages {
		stage("Start Grid") {
			steps {
				sh "docker-compose up --build -d hub chrome firefox"
			}
		}
		stage("Run Test") {
			steps {
				sh "docker-compose up --build search-module book-flight-module"
			}
		}
	}
	post {
		always {
			archiveArtifacts artifacts: 'output/**'
			sh "docker-compose down"
		}
	}
}