pipeline {
	agent none
    stages {
         stage('Build') {
		 agent {docker { image 'pooja1989/maven-sonar:latest' } }             
            steps {		
                 git credentialsId: 'GitHub', url: 'https://github.com/Tonyamoljose/InformationCenter.git'
                sh 'mvn -X clean deploy'      
            }
        } 
         
    }
}
