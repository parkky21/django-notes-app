@Library('Shared') _
pipeline {
    agent {label 'sukuna'}

    stages {
        stage('Code') {
            steps {
                
                script{
                    code_checkout('https://github.com/parkky21/django-notes-app.git','main')
                }
                
            }
        }
        stage('Build') {
            steps {
                script{
                    docker_build("notes-app","latest","parkky21")
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing stage'
            }
        }
        stage('Push') {
            steps {
                script{
                    docker_push("notes-app","latest","parkky21")
                }
               
            }
        }
        stage('Deploy') {
            steps {
                script{
                    docker_compose()
                }
            }
        }
    }
}
