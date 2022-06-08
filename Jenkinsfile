pipeline {
   agent any

   stages {
      stage('clean') {
         steps {
            bat 'mvn clean'
         }
      }
      stage('package') {
         steps {
            bat 'mvn install'
         }
      }
      stage('deploy') {
         steps {
            deploy adapters: [tomcat8(credentialsId: 'e7948e20-adaa-40e8-ba78-412ef5fe332e', path: '', url: 'http://localhost:9999')], contextPath: 'pipeline', war: 'productweb\\target\\productweb.war'         }
      }
   }
  
}
