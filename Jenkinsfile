pipeline {
    agent any

    stages { 
        
             
        stage('Build with maven') {
            steps {
          
                sh 'cd mvn MywebApp && mvn clean install'
            }
        }
        
             stage('Test') {
            steps {
                sh 'cd MywebApp && mvn test'
            }
        
            }
        stage('deploy to tomcat') {
          steps {
              deploy adapters: [tomcat9(credentialsId: 'tomcatpipeline', path: '', url: 'http://35.168.3.193:8080/')], contextPath: 'pipe', war: '**/*.war'
              
              
          }
            
        }
            
        }
} 
