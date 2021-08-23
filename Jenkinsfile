pipeline {
    agent none
    stages {
         stage('Git clone') {
            steps {
              git branch: 'main', credentialsId: 'Asp', url: 'https://github.com/jishoy-cloudjournee/App.net.git'
              sh 'ls'
            }
         }
          
         stage('Build Docker') { 
            agent {
                 // Equivalent to "docker build -f Dockerfile.build --build-arg version=1.0.2 ./build/
                 dockerfile {
                            filename 'Dockerfile'
                            label 'my-defined-label'
                            args '-t testone'
                  }
            }      
         }        
    }
}
