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
	//agent { docker { image 'maven:3.9.1'}}
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	
	stages {
		stage('Checkout') {
			steps {
				sh 'mvn --version'
				sh 'docker --version'
				echo "Checkout"
				echo "path - $PATH"
				echo "build_number - $env.BUILD_NUMBER"
			}
		}
		stage(compile) {
			steps {
				sh "mvn clean compile"
			}
		}
			stage('Test') {
			steps {
				sh "mvn test"
			}
		}
			stage('Integration Test') {
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
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
