pipeline {
	agent {
		label 'slave'
	}
	stages {
		stage('build') {
			steps {
				sh "chmod +x gradlew"				
				withGradle {					
					sh './gradlew clean build'
				}
			}
		}
		stage('image') {
			steps {
				sh "chmod +x gradlew"				
				withGradle {					
					sh './gradlew jibDockerBuild'
				}
			}
		}
	}
}