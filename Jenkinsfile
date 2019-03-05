pipeline {
	agent any
	tools {
		maven 'M3'
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
				sh "ssh opcjira@slc15gqg"
				sh "scp /var/lib/jenkins/workspace/git_file_pipeline/target/Project1-0.0.1-SNAPSHOT.jar /scratch/opcjira/."				
			}
		}
	}
}