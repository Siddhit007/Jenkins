pipeline {
    agent any

    environment {
        NAME = 'gaurav'
    }
    parameters {
        string(name: 'person', defaultValue: 'Siddhi Tilekar', description: 'Who are you?')
        booleanParam(name: 'isMale', defaultValue: 'True', description: '')
    }
    stages {
        stage('run a command') {
            steps {
                sh '''
                date
                pwd
                cal 2026
                ls
                '''
            }
        }
        stage('env variables') {
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${NAME}"'
            }
        }

        stage('parameters') {
            steps {
                echo "${params.person}"
                sh 'echo "${person}"'
                echo "${params.isMale}"
                sh 'echo "${isMale}"'
            }
        }
        stage('Continue?') {
            input{
                message "Should we continue?"
                ok "yes we should"
            }
            steps {
                echo 'deploy on prod'
            }
            }
    }
    post { 
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


