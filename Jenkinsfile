node {
   def mvnHome 
   stage('Git Clone') { 
      git 'https://github.com/brunooon/spring-app.git'
      mvnHome = tool 'maven-3.5.3'
   }
   stage('Build') {
      sh "'${mvnHome}/bin/mvn' -DskipTests clean package"
   }
   stage('Notify') {
      echo 'Sending email to developers'
   }
}
