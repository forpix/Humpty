node {
	try {
		stage ('checking for the running container') { 
			node ('Sailfish1') {
					def conta_Num = sh(returnStdout: true, script: 'docker ps -a| grep alpine | wc -l')
					if (conta_Num >= 1) { 
						//If the condition is true print the following statement 
						println("The value is less than 100"); 
						} else { 
							//If the condition is false print the following statement 
							println("The value is greater than 100"); 
						}  
			}
			}
		}
	}
	catch (exc) {
	stage ('checking fort the running containers') {
		node('master') {
					sh '''
						whoami;hostname;pwd
						b=$(docker ps -a| grep alpine | wc -l)
					if [$b -ge 1];then
						echo 'since containers are runnig exiting the node'
					else
						error 'more than one container is running so exiting the node'
					fi
					'''
			}
		}
	}
	finally {
		stage (Build) {

      sh 'Build stage'
	}

	stage (Test) {

      sh 'Test stage'
	}

	stage (Deploy) {

      sh 'Deploy stage'
	}
	
	}
}
