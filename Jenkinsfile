pipeline {
    agent any

    stages { 
        
        stage('Build with maven') {
            steps {
          
                sh 'cd SampleWebApp && mvn clean install'
            }
        }
        
             stage('Test') {
            steps {
                sh 'cd SampleWebApp && mvn test'
            }
        
            }
        
        stage('deploy to tomcat') {
          steps {
              deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://44.196.58.232:8080/')], contextPath: 'myapp', war: '**/*.war'
              
              
          }
            
        }
            
        }
} 
