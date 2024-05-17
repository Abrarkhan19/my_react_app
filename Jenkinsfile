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
    }
}
