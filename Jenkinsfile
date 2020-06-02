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
            sshPublisher(publishers: [sshPublisherDesc(configName: 'ansible', transfers: [sshTransfer(cleanRemote: false, excludes: '',
         	execCommand: 'ansible-playbook /home/ansible/capstone/kubedeploy.yml', execTimeout: 120000, flatten: false, makeEmptyDirs: false,
         	noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '//home/ansible//capstone/', remoteDirectorySDF: false, 
       	   removePrefix: 'webapp/target/', sourceFiles: 'webapp/target/*.war')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])

         }
      }
    stage('build docker image') {
        steps {
                
              sshPublisher(publishers: [sshPublisherDesc(configName: 'ansible', transfers: [sshTransfer(cleanRemote: false, excludes: '',
              execCommand: 'ansible-playbook /home/ansible/capstone/create-docker-image.yml', execTimeout: 130000, flatten: false, makeEmptyDirs: false,
              noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '',remoteDirectorySDF: false, removePrefix: '',
              sourceFiles: '')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            
             }
   
          }

      }
  }


