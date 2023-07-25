pipeline {
    agent any
    environment {
        name = "gaurav"
    }
    parameters {
        string(name: "person", defaultValue: "Nikhil Kshirsagar", description: "Who are you ?")
        booleanParam(name: "isMale", defaultValue: true, description: "")
        choice(name: "City", choices:['Achalpur', 'Paratwada', 'Amravati'], description: "")
        password(name: "PASSWORD", defaultValue: "SECRET", description: "Enter a Password")
    }

    stages {
        stage('Run a Command') {
            steps {
                sh '''
                ls
                pwd
                date
                cal 2023
                '''
            }
        }
         stage('Environment Variable') {
            environment {
                username = "Kshirsagar"
    }
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
                sh 'echo "${username}"'
            }
        }
         stage('Parameters') {
            steps {
                echo 'Deploy on Test'
                sh 'echo "${name}"'
                sh 'echo "${person}"'
            }
        }
         stage('Continue ? ') {
            input{
                message "Should we continue ?"
                ok "Yes we should"
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
        always { 
            echo 'I will always say Hello again!'
        }
        failure{
            echo 'Failure'
        } 
        success{
            echo 'Success'
        }
    }
}


