pipeline{
	agent any
	stages{
		
		stage("Start Grid"){
			steps{
				sh "docker-compose up -d hub chrome firefox"
			}
		}
		 stage("Start tests"){
                        steps{
                                sh "docker-compose up test1 test2"
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
