pipeline {
    agent {
        node {
            label 'App-Node-1'
        }
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/gajananps/osTicket.git'
            }
        }

        stage('build docker container') {
            steps {
                sh './run.sh'
            }
        }
		
    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }

        failure {
            echo 'Pipeline failed.'
        }

        always {
            echo 'Cleaning up...'
        }
    }
}
