node {
   def mvnHome
   stage('code checkout') { 
       git credentialsId: 'GitHub-ID', url: 'https://github.com/digitalorg/sonar-maven'       
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
   stage('sonarqube analysis') {
      withSonarQubeEnv(credentialsId: 'sonarqube-id'){ 
       withMaven(jdk: 'java-8', maven: 'Maven') {
           sh 'mvn sonar:sonar'
      }
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
