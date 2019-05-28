node {
	 def nod_Name = ""
	try {
		stage ('checking for the running container') { 
			node ('Sailfish1') {
					int conta_Num = sh(returnStdout: true, script: 'docker ps -a| grep alpine | wc -l')
					echo "no.of containers in node " + conta_Num
					if (conta_Num >= 1) { 
						//If the condition is true print the following statement 
						error 'Containers are running'
						} else { 
							//If the condition is false print the following statement 
							println("The value is greater than 100"); 
						}  
					}
			}
		}
	
	catch (exc) {
	stage ('checking fort the running containers') {
		node('master') {
			int conta_Numbs = sh(returnStdout: true, script: 'docker ps -a| grep alpine | wc -l')
			echo "no.of containers in node " + conta_Numbs
			if (conta_Numbs >= 1) { 
				meta ()
				//If the condition is true print the following statement 
				error 'Containers are running';
				} else { 
				//If the condition is false print the following statement 
				println("The value is greater than 100"); 
				}  
			}
		}
	}
	def meta () =
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
