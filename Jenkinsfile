node {
   	
   
   

   
 
   
	
   stage('Mvn Package'){
	   // Build using maven
	   def mvn = tool name: 'maven', type: 'maven'
	   sh "${mvn}/bin/mvn package"
   }
   
   stage('deploy-dev'){
       def tomcatDevIp = '35.153.16.158'
	   def tomcatHome = '/opt/tomcat8/'
	   def webApps = tomcatHome+'webapps/'
	   def tomcatStart = "${tomcatHome}bin/startup.sh"
	   def tomcatStop = "${tomcatHome}bin/shutdown.sh"
	   
	   sshagent (credentials: ['tomcat-dev']) {
	      sh "scp -o StrictHostKeyChecking=no target/myweb*.war ec2-user@${tomcatDevIp}:${webApps}myweb.war"
          sh "ssh ec2-user@${tomcatDevIp} ${tomcatStop}"
		  sh "ssh ec2-user@${tomcatDevIp} ${tomcatStart}"
       }
   }
   
}
