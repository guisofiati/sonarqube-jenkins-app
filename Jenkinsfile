pipeline {
    agent any
    tools {
        maven 'maven-3.9.2'
    }
    stages {
        stage("Build stage") {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'jenkins-token', url: 'https://github.com/guisofiati/sonarqube-jenkins-app.git']])
                echo "cmd: mvn clean install -DskipTests"
                sh "mvn clean install -DskipTests"
            }
        }
        stage("Test stage") {
            steps {
                echo "cmd: mvn test"
                sh "mvn test"
            }
        }
        stage("Deploy stage") {
            steps {
                echo "cmd: mvn deploy"
//              sh "mvn deploy"
            }
        }
    }
}