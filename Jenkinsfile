pipeline {
    agent {
        docker {
            image 'node:12.4-alpine'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
            
        }
        stage('deploy'){
            steps{
               sh './scripts/deploy.sh'
               input message: 'Has acabado de ver el server? (Click "Proceed" para continuar)'
               sh '.scripts/kill.sh'         
            
            
            
            }   
        }
        
                    


    }
}
