pipeline{
	agent any
	stages{
               stage("Pull Latest Image"){
			steps{
				sh "docker pull chaitali2019/autoprac"
			}
		}
		
		stage("Start Grid"){
			steps{
				sh "docker-compose up -d --scale chrome=4 --scale firefox=4  chrome hub firefox"
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
