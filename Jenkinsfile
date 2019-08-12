pipeline {
    agent any
    environment {
        TEST_VAR1 = 'true'
        TEST_VAR2 = 'sqlite'
    }
    stages {
        stage('build') {
            steps {
                sh 'python --version'
                sh 'hostname'
                sh 'pwd'
                sh 'printenv'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }    
    }
}
