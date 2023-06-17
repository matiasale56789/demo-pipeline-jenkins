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



    stage('SAST-Sonarqube') {
      steps {
        withSonarQubeEnv('devsecops') {
          sh 'mvn sonarqube:sonarqube'
          sh 'cat target/sonarqube/report-task.txt'
        }

      }
    }

  }
}
