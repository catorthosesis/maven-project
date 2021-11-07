
pipeline {

    agent any
    parameters {
        string(name: 'dsfsd', defaultValue: 'George ', description: 'hello world')
    }
    stages {

        stage('Build') {
            steps {
                timeout(time:40, unit: 'DAYS') {
                    input message: "Approve this build?"
                    echo "Inside time out "
                }
                echo "Building .....${params.name}"
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