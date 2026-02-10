
pipeline {
    agent any
    tools {
        maven "M2_HOME"
        jdk "JAVA_HOME"
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/BederSaad/devops.git'
            }
        }
        stage('Build') {
            steps {
                sh "mvn clean package -Dmaven.test.skip=true"            }
        }
    }
}