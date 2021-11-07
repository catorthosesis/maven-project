
pipeline {

    agent any
    parameters {
        string(name: 'Name', defaultValue: 'George ', description: 'hello world')
        string(name: 'RELEASE', defaultValue: 'MYRELEASE', description: 'hello world')
    }
    stages {

        stage('Build') {
            when {
                anyOf { branch 'main/*'; branch 'master' }
            }

            steps {
                echo "${params.RELEASE}....."
                def val = expression { params.RELEASE}
                echo ${val}
                timeout(time:40, unit: 'DAYS') {
                    input message: "Approve this build?"
                    echo "Inside time out "
                }
                echo "executing ....${params.RELEASE}"
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