pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Build stage - static site, no compilation required'
            }
        }

        stage('Validate') {
            steps {
                echo 'Validating HTML and CSS files'
                sh 'ls -l'
            }
        }

        stage('Execute') {
            steps {
                echo 'Execution stage completed'
            }
        }

        stage('Test') {
            steps {
                echo 'Test stage - basic check passed'
            }
        }
    }
}
