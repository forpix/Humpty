def nodes = ['Sailfish1', 'master']
def builders = [:]
for (x in nodes) {
    def node = x 

    builders[node] = {
      node(label) {
      stage ('check thd Node') {
        sh '''
           a=$(docker ps -a| grep alpine | wc -l)
           if [$a -ge 1];then
				echo 'since containers are runnig exiting the node'
           else
                echo "Running because if condition is satiedfied"
			    error
          '''
          }
		}
      }
	 }
