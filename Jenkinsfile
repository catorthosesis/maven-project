
pipeline {

    agent any
    parameters {
        strings(name: 'dsfsd', defaultvalue: '', discription: 'hello world')
    }
    stages {

        stage('Build') {
            steps {
                timeout(time:40, unit: 'DAYS') {
                    input message: "Approve this build?"
                    echo "Inside time out "
                }
                echo "Building .....$name"
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