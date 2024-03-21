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
        stage("Install npm packages") {
            steps {
                script {
                    
                    sh 'sudo apt install -y npm'
                    sh 'npm install'
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
                sh 'npm run' // Replace 'npm run build' with your actual build script
            }
        }
    }
}
