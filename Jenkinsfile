pipeline {
    agent {
        docker {
            image "adoptopenjdk/openjdk8:ubi"
            label "master"
        }
    }


    stages {
        stage("Build") {
            steps {
                sh "./gradlew -version"
                sh "./gradlew clean"
                sh "./gradlew clean build"
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}