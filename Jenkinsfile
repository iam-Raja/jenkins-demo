pipeline {
   agent {
    label 'agent 1'
   }
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 1, unit: 'MINUTES')
        disableConcurrentBuilds()
        }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

environment {
                ebv = 'prod'
            }
    

    stages {
        stage('Build') {
            steps {
                echo 'Hello World'
            }
        }
    
        stage('deploy') {
            steps {
               sh 'sleep 10'
            }
        }
        stage('release') {
            steps {
                 echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
            }
        }
    }
        post { 

        always { 
            echo 'I will always come'
        }
          failure { 
            echo 'I from failure'
        }
          success { 
            echo 'I from success'
        }

    }
    
}