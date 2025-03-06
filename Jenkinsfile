pipeline {
    agent any
    environment {
        NODEJS_HOME = tool 'NodeJS'
        PATH = "${NODEJS_HOME}/bin:${env.PATH}"
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/lulo97/JenkinNodeJsTest'
            }
        }
        stage('Install Dependencies') {
            steps {
                bash 'npm install'
            }
        }
        // stage('Run Tests') {
        //     steps {
        //         bash 'npm test || true' // Use actual test script
        //     }
        // }
        stage('Build') {
            steps {
                bash 'echo "Build completed"'
            }
        }
        stage('Deploy') {
            steps {
                bash 'nohup node app.js &'
            }
        }
    }
}
