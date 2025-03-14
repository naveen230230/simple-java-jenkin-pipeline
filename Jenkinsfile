pipeline {
	agent any	
	stages {
		stage('Checkout') {
			steps {
				git branch: 'main', credentialsId: 'github', url: 'https://github.com/naveen230230/simple-java-jenkin-pipeline.git'
			}
		}
			stage('test') {
			steps {
				echo 'Running static tests on code'
			}
		}
		stage('Build') {
			steps {
				sh 'mvn clean package'
			}
		}
		stage('Deploy') {
			steps {
				sh 'sudo cp target/*.war /opt/tomcat/apache-tomcat-9.0.68/webapps/' 
				sh 'sudo /opt/tomcat/apache-tomcat-9.0.68/bin/shutdown.sh && /opt/tomcat/bin/apache-tomcat-9.0.68/startup.sh'
			}
		}
	}
}

