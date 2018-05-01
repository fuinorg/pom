node {
   
   stage('Preparation') {
      git 'https://github.com/fuinorg/pom'
      sh "sudo /opt/jenkins/sbin/mount-webdav https://repository-fuin-org.forge.cloudbees.com/private fuin-org alert"
   }
   
   stage('Build') {
      if (isUnix()) {
         sh "./mvnw -P sonatype-oss-release -U -B -s '/private/fuin-org/settings.xml' -Dmaven.test.failure.ignore clean deploy"
      } else {
         bat(/mvnw -P sonatype-oss-release -U -B -s '/private/fuin-org/settings.xml' -Dmaven.test.failure.ignore clean deploy/)
      }
   }
   
}
