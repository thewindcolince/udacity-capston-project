pipeline {
   agent any
    tools {
    maven 'm2'
  }
   stages {
      stage('Build') {
         steps {
            sh "mvn  clean install package"
         }
       }

      stage('SendOverSsh') { 
         steps { 
            sshPublisher(publishers: [sshPublisherDesc(configName: 'ansible', transfers: [sshTransfer(cleanRemote: false, excludes: '',
         	execCommand: 'ansible-playbook /home/ansible/capstone/kubedeploy.yml', execTimeout: 120000, flatten: false, makeEmptyDirs: false,
         	noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '//home/ansible//capstone/', remoteDirectorySDF: false, 
       	    removePrefix: 'webapp/target/', sourceFiles: 'webapp/target/*.war')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])

            }
         }
      }
  }


