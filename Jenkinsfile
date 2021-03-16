pipeline {
    agent{label 'master'}
    tools{maven 'm3'}
    stages{
        stage('checkout'){
          steps{
              git branch: 'main', url:'https://github.com/AidanDillon2/SpringPetClinic.git'
          }  
        }
        stage ('Build'){
           steps{
               sh 'mvn compile'
           }
    }
       stage('Test'){
           steps{
               sh 'mvn test'
           }
       }
       Stage('Package'){
           steps{
               sh 'mvn package'
           }
       }
       stage('Deploy'){
           steps{
               sh 'java -jar /var/lib/jenkins/workspace/PetClinicDeclarativepipeline/target/*.jar'
           }
       }
    
    }
       }
