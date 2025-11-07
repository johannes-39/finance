pipeline {
    agent any  // Jenkins kann auf jedem verfügbaren Agent bauen

    environment {
        // Hier kannst du Umgebungsvariablen definieren, z.B.
        APP_NAME = "my-app"
    }

    stages {
        stage('Checkout') {
            steps {
                // Holt den Code aus dem Git-Repository
                git branch: 'main', url: 'https://github.com/johannes-39/finance.git'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying ${APP_NAME}..."
                // Beispiel: Kopieren in einen Ordner oder Docker-Deploy
                // sh 'cp target/*.jar /deploy/folder/'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
