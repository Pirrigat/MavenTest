pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git(url: 'https://github.com/Pirrigat/MavenTest.git', branch: 'master')
      }
    }
    stage('Build') {
      steps {
        tool 'Maven'
      }
    }
  }
}