node {
   
   stage('Preparation') {
      git 'https://github.com/fuinorg/pom'
      sh "sudo /opt/jenkins/sbin/mount-webdav https://repository-fuin-org.forge.cloudbees.com/private fuin-org alert"
   }
   
   stage('Build') {
      sh "./mvnw -P sonatype-oss-release -U -B --settings /private/fuin-org/settings.xml -Dmaven.test.failure.ignore clean deploy"
   }
   
}
