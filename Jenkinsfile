pipeline {
    agent any
    environment {
        list_of_images = []
    }

    stages {
        stage('Build') {
            steps {
                sh {
                    echo 'Building..'
                }
                script {
                    list_of_images.add("Item 1")
                }
            }
        }
        stage('Test') {
            steps {
                sh {
                    echo 'Testing..'
                }
                sh {
                    echo "${list_of_images}"
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
