pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /var/folders/.m2:/var/folders/.m2'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}
