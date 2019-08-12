pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'python --version'
                sh 'hostname'
                sh 'pwd'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }    
    }
}
