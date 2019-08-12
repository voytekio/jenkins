pipeline {
    agent any
    environment {
        TEST_VAR1 = 'true'
        TEST_VAR2 = 'sqlite'
    }
    stages {
        stage('build') {
            steps {
                sh 'echo running Build Stage'
            }
        }
        stage('test') {
            steps {
                sh 'echo running Test Stage'
                sh 'python --version'
                sh 'hostname'
                sh 'pwd'
                sh 'printenv'
            }
        }
        stage('deploy') {
            steps {
                sh 'echo running Deploy'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }    
    }
}
