pipeline {
    agent {
        node {
             label 'agent-1'
    }
}
    stages {
        stage('Build') {
            steps {
                echo "Building"
            }
        }
        stage('Test') {
            steps {
                echo "testing"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying"
            }
        }
    }
    post{
        always{
            echo "I will always say hello"
            cleanWs()
        }
        success {
            echo "I will run if success"
        }
        failure {
            echo "I will run if failure"
        }
    }
}

