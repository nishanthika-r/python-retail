pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://your-repo-url' // Replace with your GitHub repo
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'python -m unittest discover tests'
            }
        }

        stage('Deploy to Test Environment') {
            steps {
                echo 'Deploying to Test Environment...'
                // Add your test deployment steps here
            }
        }

        stage('Deploy to Production') {
            when {
                expression { currentBuild.result == null || currentBuild.result == 'SUCCESS' }
            }
            steps {
                echo 'Deploying to Production...'
                // Add your production deployment steps here
            }
        }
    }
}
