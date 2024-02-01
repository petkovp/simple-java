pipeline {
  agent {
    label 'maven'
  }
  stages {
    stage('Build') {
      steps {
        echo "building"
      }
    }
    stage('SonarQube Check') {
      steps {
        withSonarQubeEnv(installationName: 'SonarQube') {
          sh '''
          mvn package sonar:sonar
          '''
        }
      }
    }
  }
}
