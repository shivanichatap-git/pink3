pipeline {
	agent any 
	
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/shivani/Documents/devops/apache-maven-3.9.6/bin/mvn install'
             }}
		stage('Deployment'){
		   steps {
		sh 'cp target/pink3.war /home/shivani/Documents/devops/apache-tomcat-9.0.88/webapps'
			}}
		stage('Slack') {
			steps {
				slackSend baseUrl: 'https://hooks.slack.com/services/', 
					channel: '#pink3-slack', color: 'good', message: 'welcome to pink3 slack integration',
					notifyCommitters: true, teamDomain: 'devops', tokenCredentialId: 'pink3', username: 'pink3-slack'
			}}
	}}
