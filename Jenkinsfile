stage('Test') {
    node('Sailfish1') { 
        checkout scm
        try {
           sh '''
           a=$(docker ps -a| grep alpine | wc -l)
           if [$a -ge 1];then
            echo 'since containers are runnig exiting the node'
           else
            echo "Running because if condition is satiedfied"
           fi
           
           '''
        }
        catch (exc) {
            sh '''
            echo 'from the node'
            '''
           
        }
    }
    node('master') {
        checkout scm
        try {
            sh '''
            echo 'In to the Master Node'
           pwd;hostname;whoami
           '''
        }
        catch (exc) {
            sh '''
            echo 'coming out of the station'
            '''
           
        }
    }
}
