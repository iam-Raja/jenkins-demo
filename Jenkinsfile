pipeline {
   agent {
    label 'agent 1'
   }
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 1, unit: 'SECONDS')
    }
    stages {
        stage('Build') {
            steps {
                echo 'Hello World'
            }
        }
    }
    stages {
        stage('deploy') {
            steps {
               sh 'sleep 10'
            }
        }
    }
}