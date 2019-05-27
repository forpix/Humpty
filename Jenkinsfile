stage('Test') {
    node('Sailfish1') { 
        checkout scm
        try {
           sh '''
           pwd;hostname;whoami
           '''
        }
        catch (exc) {
            sh '''
            echo 'from the node'
            '''
            throw
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
            throw
        }
    }
}
