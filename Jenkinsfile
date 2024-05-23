pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // clean the directory
                bat "rmdir /s /q *"
                // Checkout the Git repository
                bat "git clone https://github.com/HFNSalma/CF_DevOps.git"
            }
        }
        stage('Build') {
            steps {
                // Here, we can run Maven commands
                script {
                    def currentDir = pwd()
                    echo "Current directory: ${currentDir}"
                    
                    
                     {  
                        bat 'mvn clean test package'
                        bat "java -jar target/cfProject-1.0-SNAPSHOT.jar"
                    }
                }
            }
        }
    }
}
