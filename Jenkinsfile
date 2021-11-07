
pipeline {

    agent any
    stages {

        stage('Build') {
            steps {
                timeout(time:40, unit: 'SECONDS') {
                    echo "Inside time out"
                }
                echo "Building ....."
            }
            post {
                success {
                    echo "Will execute ... "
                }

                failure {
                    echo "Will not execute.... "
                }

                }
        }


        stage('Test') {
            steps {
                echo "Testing ...."
            }
        }

        stage('Deploy') {

            steps{
                echo 'Deploying ...'
            }
        }

    }
}