pipeline {
	agent any
	stages {
		stage('SCM Checkout'){
			steps {
	               		git 'https://github.com/Abhilashreddy1995/MVN_Groovy.git'
			}
		}
		
		stage( 'Build' ) {
			steps {
				sh "mvn clean"
			}
		}
		stage( 'Sonar run' ) {
                        steps {
                                sh "mvn sonar:sonar"
                	        }
		}
		stage( 'Jfrog Deploy' ) {
                        steps {
                                sh "mvn deploy"
                        	}
		}
		stage( 'Backup of WAR file' ) {
                        steps {
                                sh "cp -pr /opt/tomcat/webapps/mygroovy /opt/tomcat/webapps/mygroovy_${date +"%d.%m.%Y"}
                                }
                }

		stage( 'Tomcat Deploy' ) {
                        steps {
                                sh "mvn tomcat7:deploy"
                        	}
		}
                stage( 'Tomcat Restart' ) {
                        steps {
                                sh "/opt/tomcat/bin/shutdown.sh"
				sh "/opt/tomcat/bin/startup.sh"
                                }
                }

	}
}
