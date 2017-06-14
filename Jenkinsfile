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
            bat 'mvn -version'
            bat 'dir'
            
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