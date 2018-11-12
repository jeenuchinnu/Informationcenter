pipeline 
  {
    environment 
       {
          registry = 'tonyamoljose/ansible_poc'
          registryCredential = 'dockerhub'
          dockerImage = ''
                }
    agent none
    stages 
       {
         stage('Build') 
	    {
	       agent 
		    { docker 
		         { image 'maven:3-jdk-8-alpine' 
		           args '-v /data/jenkins/tools/maven/.m2:/root/.m2'
                         }   
		    }
                steps 
		    {		
                        git credentialsId: 'GitHub', url: 'https://github.com/Tonyamoljose/InformationCenter.git'
                        sh 'mvn clean deploy sonar:sonar'      
                    }
            }
         stage('Building image') 
            {
               steps
		   {
                      script {
                              docker.build registry + ":$BUILD_NUMBER"
                             }
                   }
            }
	 stage(‘Deploy Image’) 
	    {
               steps
		   {
                      script {
                               docker.withRegistry( ‘’, registryCredential ) 
			           {
                                      dockerImage.push()
                                   }
                             }
                   }
            }
       }
   }
