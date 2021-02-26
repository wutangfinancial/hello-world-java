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
	stage('Tag') {
	    steps {
		script {
                	VERSION = readFile('VERSION').trim() 
		}
		sh "git config user.email \"wutangfincial@detwa.com\""
  		sh "git config --global user.name \"Dirt McGirt\""
                sh "git tag -a ${VERSION} -m \"a tag\""
                sh 'git push'
	    }
	}
    }
}
