pipeline {
    agent any
    environment {
        name = "Harman"
    }
    parameters{
        string(name: "person", defaultValue: "SIngh mr", description: "Who are you?")
        booleanParam(name: "isMale", defaultValue: true, description: "Gender?")
        choice(name: "city", choices: ['mukerian','Hsp','dubai'] , description: "Who are you?")
    }
    stages {
        stage('Run a command') {
            steps {
                sh '''
                date
                pwd
                cal 2021
                '''
            }
        }
        stage('Environment variables') {
            environment {
                username = "Singh"
            }
            steps {
                sh '''
                echo "${BUILD_ID}"
                echo "${username}"
                echo "${name}"
                '''
            }
        }
        stage('Parameters') {
           steps {
                sh '''
                echo "Deploy on Test"
                echo "${BUILD_ID}"
                echo "${name}"
                echo "${person}"
                '''
            }
        }
        stage('Continue?') {
            input{
                message "SHould we continue>"
                ok "yes we should"
            }
            steps {
                echo 'Deploy on Prod'
            }
        }
        stage('Deploy on Prod') {
            steps {
                echo 'Deploy on Prod'
            }
        }
        
    }
    post{
        always{
            echo " I will always say Hello Again!"
        }
        failure{
            echo "failure"
        }
        success{
            echo "success"
        }
    }
}
