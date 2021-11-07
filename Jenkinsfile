
pipeline {

    agent any
    stages {

        stage('Build') {
            steps {
                echo "Building ....."
            }
            post {
                success {
                    echo "Will execute ... "
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