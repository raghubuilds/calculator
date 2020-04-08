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
                sh "sudo docker build -t raghuveerk/calculator ."
            }
        }
        stage("Docker Login") {
            steps {
                sh "sudo docker login"
            }
        }
        stage('Push image') {
            steps {
             sh "sudo docker push raghuveerk/calculator"
            }
        }
    }
}
