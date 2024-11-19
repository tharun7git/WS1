pipeline {
    agent any
    environment {
        BRANCH_NAME = 'main' // Adjust according to your branch
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm  // Checkout code from the repository
            }
        }
        stage('Build') {
            steps {
                script {
                    // Command to build your project
                    sh 'mvn clean install'  // Example for Maven-based project
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Command to run your tests
                    sh 'mvn test'  // Example for Maven-based project
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    // Command to deploy your project
                    sh './deploy.sh'  // Example deployment script
                }
            }
        }
    }
    post {
        always {
            // Clean up, notify success/failure, etc.
            echo 'Pipeline completed'
        }
    }
}
