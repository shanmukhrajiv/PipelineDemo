pipeline{
    agent any
        stages{
   
           stage('Build'){
               steps{
                      git url: 'https://github.com/himajareddy506/SpringBoot.git'
             }
        }
       
        stage('Maven package'){
            steps{
       
            sh "/opt/maven/bin/mvn clean package sonar:sonar"
        }
        }
        stage('Maven deploy'){
            steps{
       
            sh "/opt/maven/bin/mvn clean deploy"
        }
        }
        
    }
}
