pipeline {
    agent any
    tools {
        maven 'maven'
    }
    stages {
        stage('build') {
            sh 'mvn compile'
        }
        stage('test') {
            sh 'mvn clean test'
        }
        stage('package') {
            sh 'mvn package -DskipTests'
        }
    }
    post {
        always {
            archiveArtifacts artifact: '**/target/*.war', onlyIfSuccessful: true
        }
    }
}