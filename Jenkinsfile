
pipeline{
    agent any
    
    tools{
        maven 'maven3.8'
    }
    
    stages{
        stage('Continuous Download'){
            steps
	    {   echo "clone the project repo"
                git branch: 'dev', credentialsId: 'git-credential', url: 'https://github.com/markondareddy/maven-web-application.git'
            }
        }
        
         stage('compile SC'){
            steps{
                sh 'mvn compile'
            }
        }
        
        stage('Generate Artifact'){
            steps{
                sh 'mvn package'
            }
        }
        
        stage('Continuous Deployment'){
            steps{
                deploy adapters: [tomcat9(credentialsId: 'tomcat-credential', path: '', url: 'http://18.207.233.240:8080/')], contextPath: 'maven-web-javaapp', war: '**/*.war'
            }
        }
        
    }
}
