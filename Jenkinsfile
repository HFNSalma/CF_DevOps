
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
                    
                    bat 'mvn clean test package'
                }
            }
        }
        stage('Run Jar') {
            steps {
                // Navigate to the target directory
                dir('target') {
                    // Run the generated jar file
                    bat "java -jar cfProject-1.0-SNAPSHOT.jar"
                }
            }
        }
    }
}
