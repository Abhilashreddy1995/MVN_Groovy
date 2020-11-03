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
		stage( 'Test' ) {
			steps {
				sh "mvn test"
			}
		}
		stage( 'Deploy' ) {
			steps {
				sh "mvn install"
			}
			}
		stage( 'Sonar run' ) {
                        steps {
                                sh "mvn sonar:sonar"
                        }
		}
		stage( 'Tomcat Deploy' ) {
                        steps {
                                sh "mvn tomcat7:deploy"
                        }
	}
}
