
pipeline {

    agent any
    parameters {
        string(name: 'Name', defaultValue: 'George ', description: 'hello world')
    }
    stages {

        stage('Build') {
            when {
                anyOf { branch 'main'; branch 'hotfix/*';branch 'master' }
                expression { params.RELEASE }
            }
            echo "executing ....${params.RELEASE}"

            steps {
                timeout(time:40, unit: 'DAYS') {
                    input message: "Approve this build?"
                    echo "Inside time out "
                }
                echo "Building .....${params.Name}"

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