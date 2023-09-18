pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Perform build steps here
                docker build -t my_react_one .
            }
        }
        
        stage('Test') {
            steps {
                // Perform test steps here
                echo "testing"
            }
        }
        
        stage('Deploy') {
            steps {
                // Perform deployment steps here
                echo "deploying"
            }
        }
    }
}
