pipeline{
	agent any
	stages{
		
		stage("Start Grid"){
			steps{
				sh "docker-compose up -d --no-colors"
			}
		}
                stage("Stop  Grid"){
                        steps{
                                sh "docker-compose down"
                        }
                }
		
	}
	post{
		always{
			archiveArtifacts artifacts: 'output/**'
			sh "docker-compose down"
			sh "sudo rm -rf output/"
		}
	}
}
