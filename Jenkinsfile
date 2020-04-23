pipeline{
	agent any
	stages{
		
		stage("Start Grid"){
			steps{
				sh "docker-compose up -d"
			}
		}
                stage("Stop  Grid"){
                        steps{
                                sh "docker-compose down"
                        }
                }
		
	}

}
