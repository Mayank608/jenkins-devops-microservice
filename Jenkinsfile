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
	agent any
	//agent { docker { image 'maven:latest'}}
	environment {
		dockerHome = 'tool myDocker'
		mavenHome = 'tool myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	
	stages {
		stage('Build') {
			steps {
				sh 'mvn --version'
				sh 'docker --version'
				echo "Build"
				echo "$PATH"
				echo "$env.BUILD_NUMBER"
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
