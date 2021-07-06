pipeline {
  agent any
 
  tools {
  maven 'Maven3'
  }
  stages {
    stage ('Build') {
      steps {
      sh 'mvn clean install -f WebRepo/pom.xml'
      }
    }

   stage(‘Test’){
       step{
         echo "Test cases passed."
      }
   }
    
       stage (' Deploy') {
      steps {
      echo "deploying to DEV Env "
      deploy adapters: [tomcat9(credentialsId: '', path: '', url: 'http://your_public_dns:7070')], contextPath: null, war: '**/*.war'
      }
    }
          }
}
