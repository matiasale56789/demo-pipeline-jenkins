pipeline {
  agent any
  stages {
    stage('Iniciando-pipeline') {
      steps {
        sh 'echo $WORKSPACE'
        sh 'chmod +x $WORKSPACE -R'
      }
    }

    stage('Check-git-secrets') {
      steps {
        sh 'docker run ghcr.io/trufflesecurity/trufflehog:latest github --repo https://github.com/digininja/DVWA.git'
      }
    }

    stage('Source-composition-analysis') {
      steps {
        sh 'rm owasp* || true'
        sh 'wget https://raw.githubusercontent.com/matiasale56789/demo-pipeline-jenkins/main/owasp-sca.sh'
        sh 'chmod +x owasp-sca.sh'
        sh 'bash owasp-sca.sh'
      }
    }

  }
}