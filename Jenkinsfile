pipeline {
	agent{
	label 'new-label'
	}
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh 'JAVA_HOME=/home/newgrras/newgrrasdir/jdk-11.0.24 /home/newgrras/newgrrasdir/apache-maven-3.9.8/mvn install'
	                 }}
		stage('Deployment'){
		    steps {
			sh 'cp target/orator.war /home/newgrras/newgrrasdir/apache-tomcat-9.0.93/webapps'
			}}	
}}

