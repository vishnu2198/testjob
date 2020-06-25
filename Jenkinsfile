node{
   stage('SCM Checkout'){
     git 'https://github.com/bhavanimahalingam/testjob'
   }
   stage('Deploy to Tomcat'){
      sshagent(['jenkins_cat']){
      sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/bavani_webapp/target/*.war  ec2-user@3.87.2.89:/home/ec2-user/apache-tomcat-9.0.36/webapps/'
      }
  }
    stage('Email Notification'){
      mail bcc: '', body: '''Hi Welcome to jenkins email alerts
      Thanks
      bhavani''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'bavani15799@gmail.com'
   }
}
   
  
