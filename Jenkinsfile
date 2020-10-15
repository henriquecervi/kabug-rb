pipeline {
    agent {
        docker {
            image 'ruby'
        }
    }
    
    stages {
        stage('Build') {
            steps {
                echo 'Building or Resolve Dependencies'
                sh 'bundle install'
            }
        }
        stage('Test') {
            steps {
                echo 'Running Regressions Tests'
            }
        }
        stage('UAT') {
            steps {
                echo 'Wait for User Acceptance'
                input(message: 'Go to Production?', ok: 'Yes')
            }
        }
        stage('Prod') {
            steps {
                echo 'WebApp is Ready :)'
            }
        }
    }
}