pipeline {
  agent any

  options {
    timestamps()
    timeout(time: 30, unit: 'MINUTES')
  }

  stages {
    stage('Verify tools') {
      steps {
        sh '''
          set -x
          which java || true
          java -version
          which mvn || true
          mvn -version
        '''
      }
    }

    stage('Build') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }
  }
}
