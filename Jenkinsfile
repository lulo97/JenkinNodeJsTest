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
                bat 'npm install'
            }
        }
        stage('Build') {
            steps {
                bat 'echo "Build completed"'
            }
        }
        stage('Deploy') {
            steps {
                // Start app.js in the background using start /B
                bat 'start /B node app.js > output.log 2>&1'
            }
        }
    }
}
