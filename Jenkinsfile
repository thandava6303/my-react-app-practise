pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/your-username/my-react-app.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build React App') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-react-app:latest .'
            }
        }
        stage('Run Container') {
            steps {
                sh 'docker run -d -p 3000:80 my-react-app:latest'
            }
        }
    }
    post {
        success {
            echo "🚀 Deployment Successful!"
        }
        failure {
            echo "❌ Deployment Failed!"
        }
    }
}
