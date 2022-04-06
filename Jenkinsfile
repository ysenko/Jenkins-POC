pipeline {
    agent any
    environment {
        LIST_OF_IMAGES = "img1,img2"
    }

    parameters {
        string(name: 'IMAGES', defaultValue: 'img_3,img_4', description: 'List of imagest to include')
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
                sh "echo ${params.IMAGES}"
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
