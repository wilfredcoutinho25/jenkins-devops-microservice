//Declarative

pipeline {
	agent any
	//agent { docker { image 'maven:latest' } }
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage ('Checkout') {
			steps {
				sh 'mvn --version'
				sh 'docker --version'
				echo 'Build stage'
				echo "$PATH"
				echo "Build_number - $env.BUILD_NUMBER"
				echo "Build_ID - $env.BUILD_ID"
				echo "Job_name - $env.JOB_NAME"
				echo "Job_URL - $env.JOB_URL"
			}
		}
		stage ('Build') {
			steps {
				sh 'mvn clean compile'
			}
		}
		stage ('Test') {
			steps {
				echo 'Test'
			}
		}
		stage ('Integration test') {
			steps {
				echo 'Integration test stage'
			}
		}
		stage ('Package') {
			steps {
				sh 'mvn package -DskipTest'
			}
		}
		stage ('Docker image build') {
			steps {
				script {
					docker.build("wilfredcoutinho25/currency-exchange-devops-jenkins:$env.BUILD_ID")
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