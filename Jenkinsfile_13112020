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

		stage( 'Tomcat backup' ) {
                        steps {
                                sh "/opt/devops/demoGroovy/warfilebackup"
                        	}
		}
                stage( 'Tomcat Deploy' ) {
                        steps {
				sh "mvn tomcat7:deploy"
                                }
                }

		stage( 'Tomcat restart' ) {
			steps {
				sh "/opt/devops/demoGroovy/tomcat_restart"
				}
		}

	}
}
