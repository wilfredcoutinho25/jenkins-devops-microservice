//Declarative

pipeline {
	agent any
	//agent { docker { image 'maven:latest' } }
	stages {
		stage ('Build') {
			steps {
				//sh 'mvn --version'
				echo 'Build stage'
				echo 'Build number - $env.BUILD_NUMBER'
				echo 'Build ID - $env.BUILD_ID'
				echo 'Job name - $env.JOB_NAME'
				echo 'Job URL - $env.JOB_URL'
			}
		}
		stage ('Test') {
			steps {
				echo 'Test stage'
			}
		}
		stage ('Integration test') {
			steps {
				echo 'Integration test stage'
			}
		}
	}
	//Post can be used for cleanup as well
	post {
		always {
			echo 'Run always'
		}
		success {
			echo 'Run when success'
		}
		failure {
			echo 'Run when failed'
		}
	}
}