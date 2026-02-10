pipeline {
  agent any
  environment {
    MAVEN_OPTS = "-Dmaven.repo.local=/var/lib/jenkins/.m2/repository"
  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }
  }
}
