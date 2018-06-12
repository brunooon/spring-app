node {
   def mvnHome 
   stage('Git Clone') { 
      git 'https://github.com/brunooon/spring-app.git'
      mvnHome = tool 'maven-3.5.3'
   }
   stage('Build') {
      sh "'${mvnHome}/bin/mvn' -DskipTests clean package"
   }
   if(env.BRANCH_NAME.equals("develop")){
      stage('Notify') {
         echo 'Sending email to developers...'
      }
   }else if(env.BRANCH_NAME.equals("master")){
      stage('Deploy') {
         echo 'Starting deploy wihth ansible...'
      }
   }
}
