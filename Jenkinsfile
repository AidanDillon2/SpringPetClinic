pipeline {
    agent{label 'master'}
    tools{maven 'M3'}
    stages{
        stage('checkout'){
          steps{
              git branch: 'main', url:'https://github.com/AidanDillon2/SpringPetClinic.git'
          }  
        }
        stage ('Build'){
           steps{
               bat 'mvn compile'
           }
    }
       stage('Test'){
           steps{
               bat 'mvn test'
           }
       }
       stage('Package'){
           steps{
               bat 'mvn package'
           }
       }
       stage('Deploy'){
           steps{
               bat 'java -jar /var/lib/jenkins/workspace/PetClinicDeclarativepipeline/target/*.jar'
           }
       }
    
    }
       }
