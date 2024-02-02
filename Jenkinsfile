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
        withSonarQubeEnv(installationName: 'SonarQube', credentialsId: 'sonarqube') {
          sh '''
          mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar
          '''
        }
      }
    }
  }
}
