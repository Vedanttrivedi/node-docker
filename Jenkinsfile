pipeline {
    agent any
    environment {
        NPM_CONFIG_PREFIX = "${WORKSPACE}/.npm-global"
        PATH = "${NPM_CONFIG_PREFIX}/bin:${PATH}"
    }
    stages {
        stage("Checkout") {
            steps {
                checkout scm
            }
        }
        stage("Setup") {
            steps {
                script {
                    sh 'sudo apt update'
                    sh 'sudo apt install -y npm'
                    sh 'npm install -g npm@latest' // Update npm to the latest version (optional)
                }
            }
        }
        stage("Test") {
            steps {
                sh 'npm test'
            }
        }
        stage("Build") {
            steps {
                sh 'npm run build' // Replace 'npm run' with the actual build script
            }
        }
    }
}
