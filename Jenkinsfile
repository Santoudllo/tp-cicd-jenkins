pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checkout du projet'
            }
        }

        stage('Build') {
            steps {
                echo 'Build terminé'
            }
        }

        stage('Test') {
            steps {
                echo 'Tests OK'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'index.html'
            }
        }

        stage('Promotion') {
            steps {
                input 'Déployer sur Alwaysdata ?'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Déploiement sur Alwaysdata'
            }
        }
    }
}