pipeline {
	agent any
	tools {
		maven 'Project1'
	}
	stages{
		stage('Checkout'){
			steps{
				git 'https://github.com/sudhakarkappala/Project1.git'
			}
		}
		stage('Build'){
			steps{
				sh 'mvn clean compile'
			}
		}
		stage('Test'){
			steps{
				sh 'mvn test'
				junit '**/target/surefire-reports/TEST-*.xml'
			}
		}
		stage('Package'){
			steps{
				sh 'mvn package'
			}
		}
	}
}