pipeline{
    
    tools{
    jdk 'JDK_8.0'    
    maven 'maven_3'
    }
   agent none 
    stages{
            
        stage('Compile'){
        agent any
        steps{
            sh 'mvn compile'
        }
            
         
    } 
        stage('Test'){
        agent any
        steps{
            sh 'mvn test'
        } 
          post{
            always{
                junit 'gameoflife-web/target/surefire-reports/*.xml'
                
            }   
          }
            
         
    } 
        stage('Package'){
        agent {label 'ubuntu16'}
        steps{
            git 'https://github.com/rdev-ops/test.git'
            sh 'mvn package'
        }
            
         
    } 

  }  
}
