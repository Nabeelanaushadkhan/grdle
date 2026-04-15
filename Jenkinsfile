pipeline {
    agent any

    stages {

        stage('Build & Test') {
            steps {
                sh 'chmod +x gradlew'
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
