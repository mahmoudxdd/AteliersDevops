pipeline {
    agent any

    tools {
        jdk 'JAVA_HOME'
        maven 'M2_HOME'
    }

    stages {

        stage('Verify tools') {
            steps {
                sh '''
                    echo "JAVA VERSION:"
                    java -version
                    echo "MAVEN VERSION:"
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
}
