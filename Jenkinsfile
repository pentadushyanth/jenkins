pipeline {
    agent {
        node {
             label 'agent-1'
    }
}
environment {
    Course = "Jenkins"
}
options {
    timeout(time: 10, unit: 'SECONDS')
}
    stages {

        stage('Build') {
            steps {
                script{ 
                    sh """ 
                        echo "building"
                        echo $Course
                        sleep 10
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
        aborted {
            echo "I will run if aborted"
        }
    }
}

