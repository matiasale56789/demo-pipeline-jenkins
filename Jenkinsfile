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
        sh 'echo $WORKSPACE'
      }
    }

    stage('SAST-Sonarqube') {
      steps {
        withSonarQubeEnv('sonarqube') {
          sh 'mvn sonar:sonar'
        }

      }
    }

  }
}