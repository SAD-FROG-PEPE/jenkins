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
                sh 'javac Main.java'
            }

        stage('Run') {
            steps {
                script {
                    sh 'java Main'
                }
            }

            post {
                success {
                    archiveArtifacts artifacts: 'main_out', fingerprint: true
                }
            }
        }
    }
}