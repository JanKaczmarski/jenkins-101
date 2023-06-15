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
                echo "doing building stuff.."
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Building.."
                sh '''
                echo "doing testing stuff.."
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