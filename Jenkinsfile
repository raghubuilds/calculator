pipeline {
    agent any
    environment {
    registry = "raghuveerk/calculator"
    registryCredential = "dockerhub"
    }
    stages {
        stage("Compile") {
            steps {
                sh "./gradlew compileJava"
            }
        }
        stage("Unit Test") {
            steps {
                sh "./gradlew test"
            }
        }
        stage("Packaging") {
            steps {
                sh "./gradlew build"
            }
        }
        stage("Docker image") {
            steps {
                sh "docker build -t raghuveerk/calculator ."
            }
        }
        stage("Docker Login") {
            steps {
                sh "docker login"
            }
        }
        stage('Push image') {
            steps {
             sh "docker push raghuveerk/calculator"
            }
        }
    }
}
