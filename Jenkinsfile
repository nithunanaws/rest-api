pipeline {
	agent {
		label 'docker-dind'
	}
	stages {		
		stage('Build Image') {
			steps {
				sh "chmod +x gradlew"				
				withGradle {					
					sh './gradlew clean build jibDockerBuild'
				}
			}
		}
		stage('Delpoy') {
			steps {
				sh 'docker run -d --name springboot-nithunan -p 9000:9000 springboot-nithunan:1.0.0-SNAPSHOT'
			}
		}
	}
}