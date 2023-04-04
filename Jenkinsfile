// scripted pipeline

// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// 	stage('Test -2') {
// 		echo "Test -2"
// 	}
// }



// Declarative pipeline
pipeline {
	//agent any
	agent { docker { image 'python:alpine3.10'}}
	stages {
		stage('Build') {
			steps {
				echo "python --version"
				echo "Build"
			}
		}
			stage('Test') {
			steps {
				echo "Test"
			}
		}
			stage('Test -2') {
			steps {
				echo "Test -2 "
			}
		}
	}

	post{
		always {
			echo "I always run"
		}
		success {
			echo "I run when you are success"
		}
		failure {
			echo "I run when you failure"
		}
	}
}
