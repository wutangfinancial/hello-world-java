pipeline {
    agent any
    options {
        timeout(time: 1, unit: 'HOURS') 
    }
    stages {
        stage('Get Info') {
            steps {
                sh 'uname -a'
            }
        }
        stage('Print Hello World') {
            steps {
                echo 'Hello World?'
            }
        }
        stage('Compile') {
            steps {
                sh 'javac HelloWorld.java'
            }
	}
        stage('Execute aka Test') {
            steps {
                sh 'java HelloWorld'
            }
	}
        stage('Tag') {
          steps {
            script {
                        VERSION = readFile('VERSION').trim() 
            }
//             sh "git config user.email \"wutangfincial@detwa.com\""
//             sh "git config --global user.name \"Dirt McGirt\""
            sh 'git fetch --tags'
            sh "git tag -a ${VERSION} -m \"a tag\""
            sh 'git push origin --tags'
            }
	  }
    }
}
