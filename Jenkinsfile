pipeline {
    agent any

    stages {
        stage('GIT HUB SCM') {
            steps {
                echo 'cloning the code from git hub'
				git branch: 'main', credentialsId: 'git', url: 'https://github.com/jhanu8191/Devops_New.git'
            }
        }
		
		
		
        stage('build Artifact') {
            steps {
                echo 'Building using maven'
				sh 'mvn clean install'
            }
        
		}
		
		
		
        stage('deploying artifact') {
            steps {
                echo 'deploying in tomcat'
				deploy adapters: [tomcat9(credentialsId: '0809bd16-0ead-40ab-9791-d0776ebda567', path: '', url: 'http://99.79.10.218:8090/')], contextPath: 'test', war: '**/*.war'
            }
        }
		}
}
