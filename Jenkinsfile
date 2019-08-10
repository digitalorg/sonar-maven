node {
   def mvnHome
   stage('code checkout') { 
       git credentialsId: 'GitHub-ID', url: 'https://github.com/digitalorg/maven_apps'
       
   }
   stage('build') {
       withMaven(jdk: 'java-8', maven: 'Maven') {
           sh 'mvn clean compile'
        }
      
   }
   stage('test') {
       withMaven(jdk: 'java-8', maven: 'Maven') {
           sh 'mvn test'
      }
      
   }
   stage('package') {
       withMaven(jdk: 'java-8', maven: 'Maven') {
           sh 'mvn package'
     }
      
   }
   stage('deploy to dev environment') {
      
   }
   stage('deploy to QA environment') {
      
   }
   stage('deploy to production environment') {
      
   }
}
