node {
	try {
		stage ('checking for the running container') { 
			node ('Sailfish1') {
					sh '''
						a=$(docker ps -a| grep alpine | wc -l)
						if [$a -ge 1];then
						echo 'since containers are runnig exiting the node'
						else
                		echo "==========Running because if condition is satiedfied========="
			    	error
					'''
			}
		}
	}
	catch (exc) {
	stage ('checking fort the running containers') {
		node('master') {
					sh '''
						b=$(docker ps -a| grep alpine | wc -l)
						if [$b -ge 1];then
						echo 'since containers are runnig exiting the node'
						else
                		echo "==========Running because if condition is satiedfied========="
						error
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
