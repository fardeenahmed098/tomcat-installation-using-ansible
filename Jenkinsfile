pipeline
{
  agent any
  stages
  { 
    stage('scm checkout')
    { steps { git 'https://github.com/fardeenahmed098/tomcat-installation-using-ansible' }}

    stage('copy playbook from jenkins workspace area to ansible master playbooks directory')
    { steps 
     { sshPublisher(publishers: [sshPublisherDesc(configName: 'ansible-master', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'ansible-playbook /etc/ansible/playbooks/tomcat-install.yml', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '//etc//ansible//playbooks', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'tomcat-install.yml')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)]) }}
  }
}
