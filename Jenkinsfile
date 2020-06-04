pipeline {

    agent any

    stages {
        stage('Enable all scripts to become executable') {
            steps {
                sh 'chmod +x /scripts/*'
            }
        }
        stage('Get the environment ready') {
            steps {
                sh './scripts/beforeinstallation.sh'
                sh './scripts/installation.sh'
            }
        }
        stage('Run the application') {
            steps {
                sh 'sudo systemctl reload flask.service'
            }
        }
    }
}