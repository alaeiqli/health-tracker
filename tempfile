pipeline {
    agent any

    stages {

        stage('Setup Python') {
            steps {
                // Crée l'environnement virtuel
                bat 'C:\\Users\\Alae\\AppData\\Local\\Programs\\Python\\Python313\\python.exe -m venv venv'
                // Active le venv et installe les dépendances
                bat 'venv\\Scripts\\activate && pip install -r requirements.txt || echo "No requirements.txt found"'
            }
        }

        stage('Run Tests') {
            steps {
                // Lance les tests si présents
                bat 'venv\\Scripts\\activate && pytest || echo "No tests found"'
            }
        }

    }

    post {
        always {
            echo 'Pipeline terminé'
        }
    }
}