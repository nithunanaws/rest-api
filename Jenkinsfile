pipeline {
	agent {
		label 'slave'
	}
	stages {
		stage('build') {
			steps {				
				withGradle {					
					sh './gradlew clean build'
				}
			}
		}
	}
}