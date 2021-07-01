
pipeline {
    agent any

    environment {
        NEW_VERSION = '1.2.0'
    }

    stages {
        stage("Build") {
            
           steps {
                        echo "building application...."
                        echo "building version ${NEW_VERSION}"
                    }
            }

        stage("test") {
             
            steps {
                  echo "testing application...."
            }
        }
         stage("deploy") {
            steps {
                    echo "deploying application...."
                    withCredentials([
                        usernamePassword(credentialsId:'test-local-credentials', usernameVariable: 'USER', passwordVariable: 'PWD')
                    ]) {
                        echo "script details ${USER} ${PWD}"
                    }
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }

    options {
                skipStagesAfterUnstable()
            }
}