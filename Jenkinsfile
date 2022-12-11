node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'Sonar-scanner';
    withSonarQubeEnv('sonarqube-9.7.1') {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
