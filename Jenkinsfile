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
				sh "docker-compose up"
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
