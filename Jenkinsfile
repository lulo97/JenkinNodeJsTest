pipeline {
    agent any
    environment {
        NODEJS_HOME = tool 'NodeJS'
        PATH = "${NODEJS_HOME}/bin:${env.PATH}"
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/lulo97/JenkinNodeJsTest'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        // stage('Run Tests') {
        //     steps {
        //         sh 'npm test || true' // Use actual test script
        //     }
        // }
        stage('Build') {
            steps {
                sh 'echo "Build completed"'
            }
        }
        stage('Deploy') {
            steps {
                sh 'nohup node app.js &'
            }
        }
    }
}
