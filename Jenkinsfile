//Declarative

pipeline {
	agent any
	stages {
		stage ('Build') {
			steps {
					echo 'Build stage'
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