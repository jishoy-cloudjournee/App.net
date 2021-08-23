pipeline {
    agent any
    stages {
         stage('Gits') {
           steps {
              sh 'git credentialsId: 'Asp', url: 'https://github.com/jishoy-cloudjournee/App.net.git'   
            }
         }
    }
}
