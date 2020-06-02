pipeline {
   agent any

   tools{
      maven "maven"
   }
   stages {
      stage('Build') {
         steps {
            sh "mvn clean install package "
         }
       }
      stage("SendOverSsh") {
         sh "echo 'sendind file over ssh' "
      }

      }
  }


