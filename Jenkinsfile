
pipeline {

    agent any
    parameters {
        string(name: 'Name', defaultValue: 'George ', description: 'hello world')
        string(name: 'RELEASE', defaultValue: 'MYRELEASE', description: 'hello world')
    }
    stages {

        stage('Build') {

            steps {
                echo "${params.RELEASE}....."

                timeout(time:40, unit: 'DAYS') {
                    input message: "Approve this build?"
                    echo "Inside time out "
                }
                echo "executing ....${params.RELEASE}"
                echo "Building .....${params.Name}"
                echo "Build ${env.BUILD_ID}"
                sh "mvn clean package"
                sh "docker build . -t tomcatwebapp:${env.BUILD_ID} "

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