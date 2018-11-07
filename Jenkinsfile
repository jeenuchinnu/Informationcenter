pipeline {
	agent none
    stages {
         stage('Build') {
		 agent {docker { image 'maven:3-jdk-8-alpine' 
		 args '-v $HOME/.m2:/data/jenkins/tools/hudson.tasks.Maven_MavenInstallation/maven1/conf'
			       } }
            steps {		
                 git credentialsId: 'GitHub', url: 'https://github.com/Tonyamoljose/InformationCenter.git'
                sh 'mvn clean deploy  -Dmaven.test.skip=true'      
            }
        } 
         
    }
}
