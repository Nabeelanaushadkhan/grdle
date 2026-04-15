pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Nabeelanaushadkhan/Gradle_2.git'
            }
        }

        stage('Setup Permissions') {
            steps {
                sh 'chmod +x gradlew'
            }
        }

        stage('Clean Build') {
            steps {
                sh './gradlew clean build'
            }
        }

        stage('Test') {
            steps {
                sh './gradlew test'
            }
        }

        stage('Run Application') {
            steps {
                sh './gradlew run'
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: 'build/libs/*.jar', fingerprint: true
            }
        }
    }

    post {
        success {
            echo '✅ Build SUCCESSFUL'
        }
        failure {
            echo '❌ Build FAILED'
        }
        always {
            echo '📌 Pipeline execution completed'
        }
    }
}
