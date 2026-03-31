pipeline {
    agent {
        node {
             label 'agent-1'
    }
}
environment {
    Course = "Jenkins"
}
    stages {

        stage('Build') {
            steps {
                script{ 
                    sh """ 
                        echo "building"
                        echo $Course
                    """
                    }
                
                echo "Building"
            }
        }
        
        stage('Test') {
            steps {
                script{ 
                    sh """ 
                        echo "building"
                    """
                    }
                echo "testing"
            }
        }
        stage('Deploy') {
            steps {
                script{ 
                    sh """ 
                        echo "building"
                    """
                    }
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

