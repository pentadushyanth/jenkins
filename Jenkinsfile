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
    timeout(time: 30, unit: 'SECONDS')
    disableConcurrentBuilds()
}

parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        //this is build section
        stage('Build') {
            steps {
                script{ 
                    sh """ 
                        echo "building"
                        echo $Course
                        sleep 5
                        env

                        echo "Hello ${params.PERSON}"
                        echo "Biography: ${params.BIOGRAPHY}"
                        echo "Toggle: ${params.TOGGLE}"
                        echo "Choice: ${params.CHOICE}"
                        echo "Password: ${params.PASSWORD}"
            
                    """
                    }
                
                echo "Building"
            }
        }
        // this is test section
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
                input {
                    message "Should we continue?"
                    ok "Yes, we should."
                    submitter "alice,bob"
                    parameters {
                        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                    }
            }
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

