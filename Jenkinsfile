pipeline {
    agent any
    tools {nodejs "my-nodejs"}
    environment {
        NODE_ENV = "production"
    }
    stages {
        stage('Hello') {
            environment{
                NODE_ENV = "develop"
            }
            steps {
                echo NODE_ENV
                git branch: 'main', url: 'https://github.com/vaibhav-mohite/jenkins-demo.git'
                echo 'The content of this file is :'
                sh 'cat demofile.txt'
            }
        }
        stage('prod') {
            steps {
                echo NODE_ENV
                sh 'npm install'
            }
        }
        stage('myartifact') {
            steps {
                archiveArtifacts artifacts: '**', followSymlinks: false
            }
        } 
    }
    
}
