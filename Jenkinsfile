pipeline {
    agent any
    
    tools{
         //configure build tools
        maven 'maven3.8.6'
    }

    stages {
        stage('scm') {
            steps {
               git branch: 'dev', credentialsId: 'git-credentials', url: 'https://github.com/markondareddy/maven-web-application.git'
            }
        }   
        
        stage('compile') {
            steps {
               echo 'compile the source code'
               bat 'mvn compile'
            }
        } 
        
         stage('Artifact') {
            steps {
               echo 'Generating artifact file'
               bat 'mvn package'
            }
        } 
        
         stage('Deploy') {
            steps {
               echo 'compile the source code'
             // deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://localhost:8090/')], contextPath: 'maven-web-application', war: '**/*.war'
              
            }
        } 
        
    }
}
