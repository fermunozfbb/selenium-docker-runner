/*
pipeline{
	agent any
	stages{
		stage("Pull Latest Image"){
			steps{
				sh "docker pull fermunoz/selenium-docker"
			}
		}
		stage("Start Grid"){
			steps{
				sh "docker-compose up -d hub chrome firefox"
			}
		}
		stage("Run Test"){
			steps{
				sh "docker-compose up search-module book-flight-module"
			}
		}
	}
	post{
		always{
			sh "docker-compose down"
		}
	}
}*/


pipeline{
	agent any
	stages{
		stage("Start Grid"){
			steps{
				sh "docker-compose up -d hub chrome firefox"
			}
		}
		stage("Run Test"){
			steps{
				sh "docker-compose up search-module book-flight-module"
			}
		}
		
	}
	post{
		always{
			archiveArtifacts artifact: 'output/**'
			sh "docker-compose down"

		}
	}
}

