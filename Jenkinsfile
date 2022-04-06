pipeline {
    agent any
    environment {
        LIST_OF_IMAGES = "img1,img2"
    }

    stages {
        stage('Build') {
            steps {
                sh "echo 'Building...'"
            }
        }
        stage('Test') {
            steps {
                sh "echo 'Testing...'"
            }
        }
        stage('Deploy') {
            steps {
                sh "echo 'Deploying....'"
                sh "echo '${LIST_OF_IMAGES}'"
            }
        }
    }
}
