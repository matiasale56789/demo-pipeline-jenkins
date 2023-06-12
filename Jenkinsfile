pipeline {
  agent any
  stages {
    stage('Iniciando-pipeline') {
      steps {
        sh 'echo $WORKSPACE'
      }
    }

    stage('Check-git-secrets') {
      steps {
        sh 'docker run ghcr.io/trufflesecurity/trufflehog:latest github --repo https://github.com/matiasale56789/demo-pipeline-jenkins.git'
      }
    }

    stage('Source-composition-analysis') {
      steps {
        sh 'wget https://raw.githubusercontent.com/matiasale56789/demo-pipeline-jenkins/main/owasp-sca.sh'
        sh 'chmod +x owasp-sca.sh'
        sh 'chown jcano:jcano odc-reports/ -R'
        sh 'bash owasp-sca.sh'
      }
    }

  }
}