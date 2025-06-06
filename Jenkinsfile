pipeline {
    agent any

    environment {
        NODE_ENV = 'development'
    }
    
    tools {
        nodejs '23.11.0'
    }
    // triggers {
    //     pollSCM('H/2 * * * *') // Check every 5 minutes for changes
    // }
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
                bat 'npm install'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment stage (add your deploy steps here)...'
                bat 'npm run build'
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
