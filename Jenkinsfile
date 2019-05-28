def spinningUpContainer(String a) {
       sh 'docker run -d --name qe1instance --hostname localContainer alpine'
        echo a
}
def runningInsideConta(String b) {
       sh 'docker exec qe1instance hostname'
        echo a
}
def removingConta(String c) {
       sh 'docker stop '
        echo a
}



node {
   try {
	stage ('checking for the running container') { 
	   node ('Sailfish1') {
		int conta_Num = sh(returnStdout: true, script: 'docker ps -a| grep alpine | wc -l')
		echo "no.of containers in node " + conta_Num
		if (conta_Num >= 1) { 
		//If the condition is true print the following statement
		echo '======  =========  ==========  ============'
		spinningUpContainer('Container Name')
		runningInsideConta('Run the conta')
		removingConta('removing It')	
		echo '+++ ++++++++++  ++++++++++++++++++ ++++'
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
		//If the condition is true print the following statement 
		sleep 15
		} else { 
		//If the condition is false print the following statement 
		println("The value is greater than 100");
			}  
		   }
	     }
      }
	node {
showMavenVersion('stagees')
    parallel parallelStagesFromMap

    generateStage("skipped") // no invocation, stage is skipped

    generateStage("nonparallel").call()
}
}
	  
	 




