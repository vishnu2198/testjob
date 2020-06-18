pipeline{
	agent any
	tools {
		jdk '1.8.0_252'
	}
	options {
		timestamps()
		
	}
	stages {
		stage('Display the path of jenkins'){
			steps {
				echo "this is building an job"
				echo "PATH = ${PATH}"
			}
		}
		stage('check the source code'){
			steps{
				checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Nirmalraaj/Jenkins.git']]])
			}
		}
		stage('run the python code'){
			steps {
				sh 'python helloworld.py'
			}
		}
		stage('email notifictaion'){
			steps {
				mail bcc: '', body: 'some error has occured', cc: '', from: '', replyTo: '', subject: 'bavani Pipeline', to: 'bavani15799@gmail.com'
	
			}
		}
	}
}
