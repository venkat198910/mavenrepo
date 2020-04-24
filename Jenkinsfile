pipeline{
agent any
   stages{
	stage("Checkout"){
		steps{
			checkout([$class: 'GitSCM', 
    branches: [[name: '*/master']], 
    userRemoteConfigs: [[credentialsId: 'c1c9644e-3114-4e06-8a60-19961f3f69f0', url: 'https://github.com/devopsamar/mavenrepo.git']]
])


		}// close steps for stage1
	   }// close for stage1
	stage("Build"){
		steps{
	         sh '/usr/local/src/apache-maven/bin/mvn package'

		}// close steps for stage2
	   }//close for stage2
       
	}//close for stages

}//close for pipeline
