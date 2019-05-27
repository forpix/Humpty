stage('Test') {
    node('Sailfish1') { 
        checkout scm
      
           sh '''
           a=$(docker ps -a| grep alpine | wc -l)
           if [$a -ge 1];then
            echo 'since containers are runnig exiting the node'
           else
            echo "Running because if condition is satiedfied"
            node('master') {
                hostname;whoami
            echo '===================getting in to second node========================='
           b=$(docker ps -a| grep alpine | wc -l)
           if [$b -ge 1];then
            echo 'since containers are runnig exiting the node'
           else
            echo "Running because if condition is satiedfied"
           fi
           }
                '''  
        
    }
}
