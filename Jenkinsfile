pipeline {
    agent any
    

    stages {
        stage('Clone') {
            steps {
                echo 'Cloning repository...'
            }
        }

        stage('Install') {
            steps {
                echo 'Installing dependencies...'
               
                bat 'npm install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
           
                bat 'npm run check'
            }
            post {
                success {
                    echo 'Tests passed successfully.'
                }
                failure {
                    echo 'Tests failed. Marking pipeline as failed.'
                    error('Tests failed.')
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution completed.'
        }
    }
}
