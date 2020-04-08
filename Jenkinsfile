pipeline {
    agent any
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
                sh "docker build -t raghuveerk/calculator:v1 ."
            }
        }
         stage("Docker login") {
            steps {
                sh "docker login"
            }
        }
        stage('Push image') {
            steps {
             sh "docker push raghuveerk/calculator:v1"
            }
        }
    }
}
