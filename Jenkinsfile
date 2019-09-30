pipeline{
    agent any
        stages{
   
           stage('Build'){
               steps{
                      git url: 'https://github.com/shanmukhrajiv/hello-world-war.git'
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
            stage('deploy_container'){
            steps{
       deploy adapters: [tomcat9(path: '', url: 'http://3.92.53.107:8888/')], 
           contextPath: 'hellorajiv', war: '**/*.war'
        }
        }
        
    }
}

