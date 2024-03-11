pipeline {
    agent any

    stages {
       stage('Checkout') {
                steps {
                    checkout([$class: 'GitSCM', branches: [[name: 'main']], userRemoteConfigs: [[url: 'https://github.com/SAD-FROG-PEPE/jenkins.git']]])
                }
            }

       stage('Build') {
            steps {
                script {
                    sh 'javac Main.java'
                    sh 'java Main'
                    sh 'jar cfe Main.txt Main Main.class'
                }
            }
        }

        stage('Archive') {
            steps {
                script {
                    archiveArtifacts artifacts: 'Main.txt', fingerprint: true
                }
            }
        }
    }
}