pipeline {
	agent any

	tools {
		maven "Maven"
	}

	stages {
		stage('cleanpackage'){
			steps {
				sh 'mvn clean package'
			}
		}
	}
}