pipeline {
    agent {label 'jdk11'}
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage ('git clone') {
            steps {
                git url: 'https://github.com/srinudammalapati/saleor.git',
                branch: 'main'
            }

        }
         stage ('docker image build') {
            steps {
               sh 'docker image build -t saleor:1.0 .'
               sh 'docker image tag saleor:1.0 8688735853/saleor:1.0 '
            }

        }
        stage ('docker image push') {
            steps {
               sh 'docker image push 8688735853/saleor:1.0'
            }

        }

    }
}      
  