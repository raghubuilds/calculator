pipeline {
    agent any
    environment {
    registry = "docker.aadyantha.com:5000/calculator"
    registryCredential = ‘docker-registry’
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
        stage("Push Image") {
            steps {
                sh "docker push 
    }
}
