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
         steps {
         sh "echo 'sendind file over ssh' "
         }
      }

      }
  }


