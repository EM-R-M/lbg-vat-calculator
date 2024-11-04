pipeline {
  agent any

  stages {
    stage('Checkout') {
      // Get some code from a GitHub repository
      git branch: 'main', url: 'https://github.com/EM-R-M/lbg-vat-calculator.git'
    }
    stage('SonarQube Analysis') {
      environment {
        scannerHome = tool 'sonarqube'
      }
      steps {
        withSonarQubeEnv('sonar-qube-1') {
          sh "${scannerHome}/bin/sonar-scanner"
        }
      }
    }
  }
}
