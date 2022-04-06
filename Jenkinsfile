def paralleStages = [:]
def dindImagesToBuild = []

pipeline {
    agent any
    environment {
        LIST_OF_IMAGES = "img1,img2"
    }

    parameters {
        string(name: 'IMAGES', defaultValue: 'img_3,img_4', description: 'List of imagest to include')
    }

    stages {
        stage("Build parallel") {
            steps {
                script {
                    def images = parameters.IMAGES
                    images.split(",").each { img -> dindImagesToBuild.add(img.trim()) }

                    dindImagesToBuild.each { img ->
                        parallelStages[img] = {
                            stage(img) {
                                sh('echo "Building image: ${img}"')
                            }
                        }
                    }
                    
                    parallel parallelStages
                }
            }
        }
    }
    // stages {
    //     stage('Build Parallel') {
    //         steps {
    //             sh "echo 'Building...'"
    //         }
    //     }
    //     stage('Test') {
    //         steps {
    //             sh "echo 'Testing...'"
    //             script
    //             sh "echo ${params.IMAGES}"
    //         }
    //     }
    //     stage('Deploy') {
    //         steps {
    //             sh "echo 'Deploying....'"
    //             sh "echo '${LIST_OF_IMAGES}'"
    //         }
    //     }
    // }
}
