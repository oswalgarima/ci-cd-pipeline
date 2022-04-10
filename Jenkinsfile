pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'Hello world, this is multibranch pipeline for Dev branch'
            }
        }
        stage('test') {
            steps {
                echo 'testing Dev...'
                docker build . --file Dockerfile --tag my-image-name:$(date +%s)
            }
        }
        stage('deploy') {
            steps {
                echo 'deploying Dev...'
            }
        }
    }
}   
