//Declarative

pipeline {
	agent any
	stages {
		stage ('Build') {
			steps {
				step {
					echo 'Build stage'
				}
			}
		}
		stage ('Test') {
			steps {
				step {
					echo 'Test stage'
				}
			}
		}
		stage ('Integration test') {
			steps {
				step {
					echo 'Integration test stage'
				}
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