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
	post {

		failure {
			discordSend description: "${BUILD_URL}", footer: 'Echec - Robin', image: '', link: '', result: 'FAILURE', thumbnail: '', title: "${env.JOB_NAME}-${BUILD_NUMBER}", webhookURL: 'https://discordapp.com/api/webhooks/747819422705778738/dHWPHidlNLpiiKftWU84__Ss2LAkws77Swfdk5OWs22qla3hlI1B4zywW8ROg4nAwjRM'
		}
		
		success {
			script {
				if ("${env.BRANCH_NAME}" == 'master')
					discordSend description: "${BUILD_URL}", footer: 'Success - Robin', image: '', link: '', result: 'SUCCESS', thumbnail: '', title: "${env.JOB_NAME}-${BUILD_NUMBER}", webhookURL: 'https://discordapp.com/api/webhooks/747819422705778738/dHWPHidlNLpiiKftWU84__Ss2LAkws77Swfdk5OWs22qla3hlI1B4zywW8ROg4nAwjRM'
			}
		}
	}
}