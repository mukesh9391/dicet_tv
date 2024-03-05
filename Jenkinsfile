pipeline {
    agent any

    stages {
        stage('code from github') {
            steps {
                git 'https://github.com/BHUPESHGCTECH/dicet_tv.git'
            }
        }
        stage('Build the code') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'pipeline', path: '', url: 'http://16.16.193.159:8081/')], contextPath: 'mukesh', war: '**/*.war'
            }
        }
    }
}
