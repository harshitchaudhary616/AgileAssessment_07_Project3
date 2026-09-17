
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/harshitchaudhary616/AgileAssessment_07_Project3.git'
            }
        }

        stage('Parallel Checks') {
            parallel {
                stage('Frontend Check') {
                    steps {
                        sh 'python frontend_check.py'
                    }
                }

                stage('Backend Check') {
                    steps {
                        sh 'python backend_check.py'
                    }
                }
            }
        }

        stage('Summary') {
            steps {
                echo 'Both frontend and backend checks are complete.'
            }
        }
    }
}
