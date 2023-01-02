pipeline{
    agent any
    tools{
        maven "maven 3.8"
    }
    
    stages{
        stage('scm'){
            steps{
                git credentialsId: 'git-credentails', url: 'https://github.com/markondareddy/maven-web-application.git'
            }
            
        }
        
        stage('compile-code'){
            steps{
                sh 'mvn compile'
            }
            
        }
        
        
        
         stage('package'){
            steps{
                sh 'mvn package'
            }
            
        }
        
        stage('Artifact') {
            steps {
                // maven artifacts
               archiveArtifacts 'target/*.war'
            
            }
        }
        
        // stage('sonarqube') {
            //steps {
        //  withSonarQubeEnv('jenkins-sonarqube') {
               //sh 'mvn sonar:sonar'  
         //  }
       // }
       
   // }
    
    }
}
