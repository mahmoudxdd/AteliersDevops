pipeline {
    agent any

    tools {
        maven 'Maven'  
        jdk 'Java'
    }

    stages {

        stage('Clone Repository') {
            steps {
                echo "Cloning GitHub project..."
                git branch: 'main', url: 'https://github.com/mahmoudxdd/AteliersDevops'
            }
        }

        stage('Build Project') {
            steps {
                echo "Building Java project..."
                sh 'mvn clean package'
            }
        }

        stage('Run Application') {
            steps {
                echo "Running Java application..."
                sh 'java -jar target/*.jar'
            }
        }
    }

    post {
        success {
            echo " Project executed successfully!"
        }
        failure {
            echo " Build failed!"
        }
    }
}
