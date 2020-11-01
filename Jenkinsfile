pipeline {
	agent any
	stages {
		stage('SCM Checkout'){

                  git 'https://github.com/Abhilashreddy1995/MVN_Groovy.git'

		stage{ 'Build' } {
			steps {
				sh "mvn clean"
			}
		}
		stage { 'Test' } {
			steps {
				sh "mvn test"
			}
		}
		stage{ 'Deploy' } {
			steps {
				sh "mvn install"
			}
		{
	}
}
