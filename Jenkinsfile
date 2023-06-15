pipeline {
    agent{
        node {
            label 'docker-agent-python'
        }
    }
    triggers {
        pollSCM 'H/5 * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                echo "Building in process.."
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                echo "$DOCKER_PASSWORD and $DOCKER_LOGIN"
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver..'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}