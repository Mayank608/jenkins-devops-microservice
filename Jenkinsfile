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
	stages {
		stage('Build') {
			steps {
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
}
