pipeline {
	agent none
    stages {
         stage('Build') {
		 agent {docker { image 'maven' 
		 args '-v $HOME/.m2:/root/.m2:z -u root'
			       } }
            steps {		
                 git credentialsId: 'GitHub', url: 'https://github.com/Tonyamoljose/InformationCenter.git'
                sh 'mvn -X clean deploy  -Dmaven.test.skip=true'      
            }
        } 
         
    }
}
