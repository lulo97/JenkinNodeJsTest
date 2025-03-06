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
        // stage('Run Tests') {
        //     steps {
        //         bat 'npm test || true' // Use actual test script
        //     }
        // }
        stage('Build') {
            steps {
                bat 'echo "Build completed"'
            }
        }
        stage('Deploy') {
            steps {
                bat 'forever stop app.js || echo "No running instance"' // Stop previous instance if any
                bat 'forever start app.js' // Start the app and keep it running
            }
        }
    }
}
