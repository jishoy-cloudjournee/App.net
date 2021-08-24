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
              withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'dockerhubPassword', usernameVariable: 'dockerhubUser')]) {
                 sh  'docker login -u ${env.dockerhubUser} -p ${env.dockerhubPassword}'
                 sh  'docker push jishoy96/aspent'
            }
         }         
  }
}
