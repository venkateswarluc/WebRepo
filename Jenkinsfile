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

   stage('Test'){
       step{
         echo "Test cases passed."
      }
   }
    
       stage ('Deploy') {
      steps {
      echo "deploying to DEV Env "
       sh 'scp WebRepo/mvnwebapp.war   ec2-user@<ip>:/home/ec2-user/tomcat/webapps/'
      }
    }
          }
}
