pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }
    
        stage('clean') {
            steps {
              sh  'mvn clean'
            }
        }
        
        stage('test') {
            steps {
              sh  'mvn test'
            }
        }
        stage('install') {
            steps {
               sh  'mvn install'
            }
        }
        
        stage('deployment') {
            steps {
                
              deploy adapters: [tomcat9(credentialsId: '0f4916c0-d978-4da9-aa3a-a73e108a9c65', path: '', url: 'http://34.201.133.127:8080/')], contextPath: 'webapp', war: 'webapp/target/*.war'

            }
        }
        
    }
}


    
