pipeline {
  agent any
  tools {
	maven "Maven"
	jdk "Java8u131"
  }
  
  stages {
  
    stage('Checkout') {
	
      steps {
	  
        parallel(
		
          "Checkout": {
		  
            git(url: 'https://github.com/Pirrigat/MavenTest.git', branch: 'master')
            
          },
          "Check": {
		  
            sh '''
				dir 
				echo "Git is now checked out!"
			   '''
            
          }
        )
      }
    }
    stage('Build') {
      steps {
        sh '''
			mvm clean package
		   '''
      }
    }
    stage('run') {
      steps {
        sh '''
			java -jar gs-maven-0.1.0.jar
		   '''
      }
    }
  }
}