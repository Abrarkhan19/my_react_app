pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                git 'https://github.com/Abrarkhan19/my_react_app.git'
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage('Deploy') {
            environment {
                AWS_DEFAULT_REGION = 'us-east-1'
                AWS_ACCESS_KEY_ID = credentials('AKIAW3PMO42WS2BBRNJJ').AWS_ACCESS_KEY_ID
                AWS_SECRET_ACCESS_KEY = credentials('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').AWS_SECRET_ACCESS_KEY
            }
            steps {
                script {
                    def region = 'us-east-1'
                    def bucket = 'abrar-s3-bucket'
                    def sourceDir = 'build'

                    sh "aws s3 sync ${sourceDir} s3://${bucket} --region ${region}"
                }
            }
        }
    }
}
