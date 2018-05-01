node {
   
   stage('Preparation') {
      git 'https://github.com/fuinorg/pom'
   }
   
   stage('Build') {
      if (isUnix()) {
         sh "./mvnw -B -Dmaven.test.failure.ignore clean package"
      } else {
         bat(/mvnw -B -Dmaven.test.failure.ignore clean package/)
      }
   }
   
}
