pipeline {
    agent any
    stages{
         stage('Git clone') {
            agent any
            steps {
              git branch: 'main', credentialsId: 'Asp', url: 'https://github.com/jishoy-cloudjournee/App.net.git'
              sh 'ls'
            }
         }
          
         stage('Build Docker') { 
             agent{ 
                 docker { image 'docker:dind'}
                }     
              steps
              {
                echo "hello"
              }
          }        
    }
}
