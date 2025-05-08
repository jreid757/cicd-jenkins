pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION = 'us-east-1'
        S3_BUCKET = 'court-status'
    }

    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/jreid757/cicd-jenkins.git', branch: 'main'
            }
        }

        stage('Upload to S3') {
            steps {
                sh '''
                    aws s3 cp index.html s3://$S3_BUCKET/index.html 
                '''
            }
        }
    }
}
