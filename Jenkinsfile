pipeline {
    agent any
    environment {
      dockerhub_cred = credentials('dockerhub')

    }
    stages{
         stage('Git clone') {
            steps {
              git branch: 'main', credentialsId: 'Asp', url: 'https://github.com/jishoy-cloudjournee/App.net.git'
              sh 'ls'
            }
         }
          
          stage('Build Docker') { 
             agent { 
                 docker { image 'docker:dind'}
              }     
              steps
              {
                sh 'docker build -t aspent .'
              }
          }
          stage('push docker'){
            steps{
              sh 'echo $dockerhub_cred_psw | docker login -u  $dockerhub_cred_usr --password-stdin'
            }

          }        
    }
}
