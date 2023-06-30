pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
        AWS_DEFAULT_REGION = "us-east-1"

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh "npm ci --production"
                sh "npm run build"
            }
        }
        stage('Push') {
            steps {
                echo 'Pushing..'
                sh 'npm run deploy'
                sh "aws s3 sync dist/angular-demo/s3://angular-ui-sj"
            }
        }
        stage('Deploy') {
            steps {
                echo ....'
            }
        }
    }
}