pipeline {
    agent any

    environment {
        NODE_ENV = 'development'
    }
    triggers{
        githubPush()
    }
    tools {
        nodejs '23.11.0'
    }

    stages {
        stage('Checkout Repository') {
            steps {
                echo 'Cloning the GitHub repository...'
                git branch: 'main', url: 'https://github.com/malhisimrat/nodejenkins.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies using Node.js 23.11.0...'
                sh 'npm install'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment stage (add your deploy steps here)...'
                sh 'npm start'
            }
        }
    }

    post {
        success {
            echo '✅ Node.js pipeline completed successfully!'
        }
        failure {
            echo '❌ Something went wrong. Please check the logs.'
        }
    }
}
