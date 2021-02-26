pipeline {
    agent any
    options {
        timeout(time: 1, unit: 'HOURS') 
    }
    stages {
        stage('Print Hello World') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Compile') {
            steps {
                sh 'javac HelloWorld.java'
            }
	}
        stage('Execute') {
            steps {
                sh 'java HelloWorld'
            }
	}
    }
}
