
pipeline {
  agent any

  options {
    timeout(time: 20, unit: 'MINUTES')
    timestamps()
  }

  tools {
    maven 'M2_HOME'   
    jdk 'JAVA_HOME'      
  }

  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/mahmoudxdd/AteliersDevops.git'
      }
    }

    stage('Build') {
      steps {
        sh 'mvn -B -U clean package -DskipTests'
      }
    }
  }
}
