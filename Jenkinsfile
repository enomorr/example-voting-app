pipeline {
    agent any
    tools{
        nodejs 'NodeJS 18.0.0'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                dir('result'){
                    sh 'npm install'

                }
                
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                dir('result'){
                    sh 'npm install'
                    sh 'npm test'
                }
                
            }
        }
}
}
