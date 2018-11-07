pipeline {
	agent none
    stages {
         stage('Build') {
		 agent {docker { image 'maven' 
		 args '-v ${HOME}/.m2/settings.xml:/data/jenkins/tools/hudson.tasks.Maven_MavenInstallation/maven1/conf/settings.xml'
			       } }
            steps {		
                 git credentialsId: 'GitHub', url: 'https://github.com/Tonyamoljose/InformationCenter.git'
                sh 'mvn -X clean deploy  -Dmaven.test.skip=true'      
            }
        } 
         
    }
}
