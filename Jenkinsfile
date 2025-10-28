pipeline {
    agent any

    environment {
        APP_NAME = 'myjavaapp'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/athrv1837/myjavaapp.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn -B clean package'
            }
        }

        stage('Run Application') {
            steps {
                bat 'java -cp target/myjavaapp-1.0-SNAPSHOT.jar com.example.App'
            }
        }
    }

    post {
        success {
            echo "Pipeline executed successfully!"
        }
        failure {
            echo "Build or run failed. Check console output."
        }
    }
}