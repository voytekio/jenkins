pipeline {
    agent any
    environment {
        TEST_VAR1 = 'true'
        TEST_VAR2 = 'sqlite'
    }
    stages {
        stage('build') {
            steps {
                sh 'echo ========================'
                sh 'echo running Build Stage'
                sh 'poetry -V'
            }
        }
        stage('test') {
            steps {
                sh 'echo ========================'                
                sh 'echo running Test Stage'
                sh 'python --version'
                sh 'hostname'
                sh 'pwd'
                sh 'printenv'
                sh 'tox'
                // sh 'exit 1'
            }
        }        
        stage('deploy') {
            steps {
                sh 'echo ========================='
                sh 'echo running Deploy Stage'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }    
    }
}
