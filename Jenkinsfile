pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh'''
                docker build -t react_one_with_pipeline .
                '''
                
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh'''
                    docker run -p 3070:80 -d react_one_with_pipeline
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}