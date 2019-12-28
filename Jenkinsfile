
pipeline{
     agent { label 'slave' }
     stages{
       stage(scm) {
           steps{
checkout([$class: 'GitSCM', 
    branches: [[name: '*/feature']], 
    userRemoteConfigs: [[credentialsId: '4a1288aa-6391-4d75-9387-f37f8a43bd1d	', url: 'https://github.com/devopsamar/mavenrepo.git']]
])
}
       } 
       stage(package){
       steps{
          sh '/usr/local/src/apache-maven/bin/mvn package' 
       }    
       }
       stage(tomcat){
           steps{
          sh 'ssh 18.188.185.28 systemctl stop tomcat'
sh 'scp /root/workspace/My_First_Job/target/studentapp-2.5-SNAPSHOT.war 18.188.185.28:/var/lib/tomcat/webapps'
sh 'ssh 18.188.185.28 systemctl start tomcat'
       }
     }
     }
         }
