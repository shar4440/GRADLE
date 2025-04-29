  pipeline {
    agent any

    tools {
        gradle 'Gradle' // Make sure Jenkins has this Gradle tool defined
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/shar4440/GRADLE.git', branch: 'master', credentialsId: 'shar4440'
            }
        }

        stage('Build') {
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

    post {
        failure {
            echo 'Build failed!'
        }
        success {
            echo 'Build successful!'
        }
    }
}
