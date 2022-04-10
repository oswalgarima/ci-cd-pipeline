pipeline {
    agent none
    stages {
        stage("Docker Permissions") {
        agent any
            steps {
                sh "sudo chmod 666 /var/run/docker.sock"
            }
        }
        stage('Build') {
            agent {
                docker {
                    image 'maven:3-alpine'
                    args '-v $HOME/.m2:/root/.m2'
                }
            }
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }
        stage('Build') {
        agent none
            steps {
                script {
                    image = docker.build("test-image", "./")
                }
            }
        }
    }
}
