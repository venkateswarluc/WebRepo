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
       sh 'cp WebRepo/mvnwebapp.war   /home/ubuntu/tomcat8/webapps/'
      }
    }
          }
}
