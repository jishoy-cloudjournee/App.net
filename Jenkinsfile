pipeline {
    agent any
    environment {
          dockerImage = ''
    }
    
    stages {
         stage('Git clone') {
            steps {
              git branch: 'main', credentialsId: 'Asp', url: 'https://github.com/jishoy-cloudjournee/App.net.git'
              sh 'ls'
            }
         }
          
         stage('Build Docker') { 
             steps {
              script {
                   dockerImage = docker.build registry
              }
             }
         }        
    }
}
