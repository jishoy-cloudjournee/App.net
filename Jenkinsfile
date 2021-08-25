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
           //  agent { 
           //      docker { image 'docker:dind'}
           //   }     
              steps
              {
                sh 'docker build -t jishoy96/aspent .'
              }
          }
          stage('push docker'){
            steps{
              sh 'echo $dockerhub_cred_PSW | docker login -u $dockerhub_cred_USR --password-stdin'
              sh  'docker push jishoy96/aspent'
            }
         }
         stage('Deploy'){
            steps{
               sshagent(['deploy']) {
                   //sh 'sudo -i'
                   sh 'ls'
                }
            }
         }
        
  }
}
