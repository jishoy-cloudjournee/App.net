pipeline {
    agent ubuntu
    stages {
         stage('Gits') {
           steps {
              git branch: 'main', credentialsId: 'Asp', url: 'https://github.com/jishoy-cloudjournee/App.net.git'
              sh 'ls'
            }
         }
    }
}
