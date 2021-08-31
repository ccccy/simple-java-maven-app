pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /var/folders/.m2:/var/folders/.m2'
        }
    }
    stages {
        stage('test') {
            steps {
                sh 'mvn --v'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}
