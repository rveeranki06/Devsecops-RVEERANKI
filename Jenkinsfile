pipeline {
  agent any

  stages {
      stage('Build Artifact') {
            steps {
              sh "mvn clean package -DskipTests=true"  ##test
              archive 'target/*.jar'
            }
        }   
    }
}
