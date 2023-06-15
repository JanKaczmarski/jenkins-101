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
                docker build -t bigjack213/testImage ./myapp
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                echo "Doing testing stuff.."
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver..'
                sh '''
                echo "$DOCKER_PASSWORD" | docker login -u "$DOCKER_LOGIN" --password-stdin
                docker push bigjack213/testImage
                '''
            }
        }
    }
}