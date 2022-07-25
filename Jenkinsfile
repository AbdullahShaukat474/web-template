pipeline  {
  agent { label 'linux'}
  options  {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages  {
    steps('scan')  {
      steps  {
        withSonarQubeEnv(installationName: 'sql1')  {
          sh './mvnw clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'
        }
      }
    }
  }
}
