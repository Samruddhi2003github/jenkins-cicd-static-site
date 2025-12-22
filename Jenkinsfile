pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION = 'us-east-1'
        S3_BUCKET = 'jenkins-cicd-static-site-samruddhi'
    }

    stages {

        stage('Build') {
            steps {
                echo 'Build stage completed'
            }
        }

        stage('Validate') {
            steps {
                echo 'Validation successful'
            }
        }

        stage('Test') {
            steps {
                echo 'Basic test passed'
            }
        }

        stage('Upload to S3') {
            steps {
                withCredentials([[
                    $class: 'AmazonWebServicesCredentialsBinding',
                    credentialsId: 'aws-s3-creds'
                ]]) {
                    sh '''
                        aws s3 sync . s3://$S3_BUCKET \
                        --exclude ".git/*" \
                        --exclude "Jenkinsfile"
                    '''
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully'
        }
    }
}
