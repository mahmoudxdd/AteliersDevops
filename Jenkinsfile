pipeline {
  agent any
  environment {
    MAVEN_OPTS = "-Dmaven.repo.local=/var/lib/jenkins/.m2/repository"
  }
  stages {
    stage('Verify tools') {
      steps {
        sh '''
          java -version
          mvn -version
        '''
      }
    }
    stage('Build') {
      steps {
        sh 'mvn -B -ntp -DskipTests clean package'
      }
    }
  }
  post {
    success {
      archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
    }
  }
}
