pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /home/Documents/GitHub/.m2:/home/Documents/GitHub/.m2'
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
