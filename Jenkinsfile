pipeline {
	agent none
    stages {
         stage('Build') {
		 agent {docker { image 'pooja1989/maven_sonar:latest' } }             
            steps {		
                 git credentialsId: 'GitHub', url: 'https://github.com/Tonyamoljose/InformationCentre.git'
                sh 'mvn -X clean deploy'      
            }
        } 
         
    }
}
