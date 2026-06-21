pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
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
                input 'Déployer ?'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Déploiement effectué'
            }
        }
    }
}