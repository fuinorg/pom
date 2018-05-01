node {
   
   stage('Preparation') {
      git 'https://github.com/fuinorg/pom'
   }
   
   stage('Build') {
      if (isUnix()) {
         sh "./mvnw -P sonatype-oss-release -B -Dmaven.test.failure.ignore clean deploy"
      } else {
         bat(/mvnw -P sonatype-oss-release -B -Dmaven.test.failure.ignore clean deploy/)
      }
   }
   
}
