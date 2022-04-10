

pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
    }
    stages {
        
        stage('Initialize'){
        def dockerHome = tool 'myDocker'
        env.PATH = "${dockerHome}/bin:${env.PATH}"
    }
        
        
        
         stage('Clone repository') { 
            steps { 
                script{
                checkout scm
                }
            }
        }

        stage('Build') { 
            steps { 
                script{
                 app = docker.build("test-image", "./")
                }
            }
        }
        stage('Test'){
            steps {
                 echo 'Empty'
            }
        }
      
            }
        }
    
