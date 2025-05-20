pipeline {
	agent any
	
	tools {
		maven 'maven'
		jdk 'JDK'
	}
	
	stages {
	
		stage('Checkout') {
			steps {
				git branch: 'master', url: 'https://github.com/yuvrajandotra/MyMavenSeleniumApp.git'
			}
		}
		
		stage('Build') {
			steps {
				sh 'mvn compile package'
			}
		}
		
		stage('Test') {
			steps {
				sh 'mvn test'
			}
		}	
		
		stage('Archive Artifacts') {
			steps {
				archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
			}
		}	
	}
	
	post {
		success {
			echo 'Pipeline Successfull!'
		}
		failure {
			echo 'Pipeline Failed!'
		}
	}
}								
