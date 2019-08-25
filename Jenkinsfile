pipeline {
    agent any
    environment {
        TEST_VAR1 = 'false'
        TEST_VAR2 = 'sqlite'
        //AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
        //AWS_SECRET_ACCESS_KEY = credentials('jenkins-aws-secret-access-key')
    }
    stages {
        stage('build') {
            steps {
                sh 'echo ========================'
                sh 'echo running Build Stage'
                sh 'python --version'
                sh 'hostname'
                sh 'pwd'
                sh 'printenv'
                sh 'echo ========================'
                // sh 'curl -sSL https://raw.githubusercontent.com/sdispater/poetry/master/get-poetry.py | python'
                // sh 'poetry -V'
                sh 'groups'
            }
        }
        stage('test') {
            steps {
                sh 'echo ========================'                
                sh 'echo running Test Stage'
                // sh 'tox'
                // sh 'exit 1'
            }
        }        
        stage('DEPLOY-TAGS') {
            when {
                buildingTag()
            }
            steps {
                sh 'echo ========================='
                sh 'echo running only when Tag sent.'
            }
        }
        stage('DEPLOY-PULL_REQUEST') {
            when {
                changeRequest()
            }
            steps {
                sh 'echo ========================='
                sh 'echo running only when PR sent.'
            }
        }
        stage('DEPLOY-MERGE_INTO_MASTER') {
            when {
                branch 'master'
            }
            steps {
                sh 'echo ========================='
                sh 'echo running only when merge into master sent'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }    
    }
}
