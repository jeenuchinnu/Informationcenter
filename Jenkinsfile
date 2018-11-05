pipeline {
	agent none
    stages {
         stage('Build') {
		 agent {docker { image 'maven' } }             
            steps {		
                 git credentialsId: 'GitHub', url: 'https://github.com/Tonyamoljose/InformationCenter.git'
                sh 'mvn -X clean deploy'      
            }
        } 
         
    }
}
