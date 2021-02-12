pipeline {
	agent any  
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
		stage("Stop Grid") {
			steps {
				sh "docker-compose down"
			}
		}
	
	}
}