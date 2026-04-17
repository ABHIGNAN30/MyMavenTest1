pipeline {
    agent any

    tools {
        maven 'Maven'  
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: ''
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'  
            }
        }

        
        
       
        stage('Run Application') {
            steps {
                
                sh 'mvn clean compile exec:java -Dexec.mainClass="com.example.App"'
            }
        }

        
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
