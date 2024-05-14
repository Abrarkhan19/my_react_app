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
            steps {
                withAWS(credentials: '471331694253', region: 'us-east-1') {
                    s3Upload(bucket: 'abrar-s3-bucket', file: 'build/**')
                }
            }
        }
    }
}
