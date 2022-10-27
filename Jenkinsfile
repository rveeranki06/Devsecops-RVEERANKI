pipeline {
  agent any

  stages {
      stage('Build Artifact') {
            steps {
              sh "mvn clean package -DskipTests=true"
              archive 'target/*.jar'
            }
        }
    stages {
        stage('git version') {
            steps {
                sh 'git version'
            }
        }
        stage('maven version') {
            steps {
                sh 'mvn -version'
            }
        }
        stage('docker version') {
            steps {
                sh 'docker --version'
            }
        }
        stage('kubectl version') {
            steps {
                withKubeConfig([credentialsId: 'kubeconfig1']) {
                sh 'kubectl version'
            }
        }
