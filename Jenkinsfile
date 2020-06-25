node{
   stage('SCM Checkout'){
     git 'https://github.com/bhavanimahalingam/testjob'
   }
   stage('Deploy to Tomcat'){
      
    sshagent(['tomcat_jenkins'])
    sh 'ssh -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/bavani_webapp/target
/*.war  ec2-user@34.202.233.126:/home/ec2-user/apache-tomcat-7.0.104/webapps/'
  }
   }
   stage('Email Notification'){
      mail bcc: '', body: '''Hi Welcome to jenkins email alerts
      Thanks
      bhavani''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'bavani15799@gmail.com'
   }
   

}
