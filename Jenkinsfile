pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                git 'https://github.com/SAD-FROG-PEPE/jenkins_task.git'
                sh "mvn -Dmaven.test.failure.ignore=true clean package"
            }

            post {
                success {
                    archiveArtifacts 'target/*.jar'
                }
            }
        }
    }
}