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
           sh 'mvn sonar:sonar -Dsonar.projectKey=sonar-maven -Dsonar.organization=digitalorg -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=cd3439ae3a30b5f20a1fe97b7a8af35d587fbe16'
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
