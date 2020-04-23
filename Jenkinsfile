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
                stage("Stop  Grid"){
                        steps{
                                sh "docker-compose down"
                        }
                }
		
	}

}
