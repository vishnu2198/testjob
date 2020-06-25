node{
   stage('SCM Checkout'){
     git 'https://github.com/bhavanimahalingam/testjob'
   }
   stage('Deploy to Tomcat'){
      sshagent(['tomcat_jenkins']){
      sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/bavani_webapp/target/*.war  ec2-user@3.87.2.89:/home/ec2-user/apache-tomcat-9.0.36/webapps/'
      }
  }
}
   
  
