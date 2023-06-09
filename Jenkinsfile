pipeline {
    agent any
    stages {
        stage('Iniciando-pipeline'){
            steps {
            sh'echo $WORKSPACE'
        }
    }
        stage('Check-git-secrets'){
            steps {
            sh 'docker run ghcr.io/trufflesecurity/trufflehog:latest github --repo https://github.com/digininja/DVWA.git'
        }
    }    
}
}
