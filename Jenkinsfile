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

		stage( 'Tomcat Deploy' ) {
                        steps {
                                sh "mvn tomcat7:deploy"
                        	}
		}
                stage( 'Tomcat Restart' ) {
                        steps {
                                sh "su root -c '/opt/tomcat/bin/shutdown.sh'"
				sh "sleep 4000"
				sh "su root -c `'/opt/tomcat/bin/startup.sh'"
                                }
                }

	}
}
