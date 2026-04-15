pipeline {
    agent any

    stages {

        stage('Build & Test') {
            steps {
                sh './gradlew build'
            }
        }

        stage('Run') {
            steps {
                sh './gradlew run'
            }
        }
    }
}
