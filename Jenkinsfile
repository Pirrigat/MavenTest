pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        parallel(
          "Checkout": {
            git(url: 'https://github.com/Pirrigat/MavenTest.git', branch: 'master')
            
          },
          "Check": {
            sh '''mvn -version
echo "Hello"'''
            
          }
        )
      }
    }
    stage('Build') {
      steps {
        tool 'Maven'
      }
    }
  }
}