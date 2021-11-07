
pipeline {

    agent any
    parameters {
        string(name: 'Name', defaultValue: 'George ', description: 'hello world')
    }
    stages {

        stage('Build') {
            steps {
                timeout(time:40, unit: 'DAYS') {
                    input message: "Approve this build?"
                    echo "Inside time out "
                }
                echo "Building .....${params.Name}"

                when {
                    anyOf { branch 'main'; branch 'hotfix/*';branch 'master' }
                    expression { params.RELEASE }
                }
                echo "executing ....${params.RELEASE}"
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