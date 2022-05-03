pipeline {
    agent any
    tools{
        maven 'Maven 3.8.5'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                dir('worker'){
                    sh 'mvn compile'

                }
                
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                dir('worker'){
                    sh 'mvn test'
                }
                
            }
        }
        stage('Package') {
            steps {
                echo 'Packaging....'
                dir('worker'){
                    sh 'mvn package -DskipTests'
                }
                
            }
        }
    }
    post{
       always{
          archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
          echo 'This was successfully built and packaged'
    }
}
    
}
