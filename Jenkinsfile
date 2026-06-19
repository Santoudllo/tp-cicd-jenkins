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
                input 'Déployer sur Alwaysdata ?'
            }
        }

        stage('Deploy') {
            steps {
                sshagent(credentials: ['alwaysdata-ssh']) {
                    sh '''
                        scp -o StrictHostKeyChecking=no index.html \
                        projetcicd@ssh-projetcicd.alwaysdata.net:~/www/
                    '''
                }
                echo 'Déploiement terminé'
            }
        }
    }
}