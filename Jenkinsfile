node {
   
   stage('Code Checkout') { // for display purposes
    git credentialsId: 'githubID', url: 'https://github.com/Shrij34/maven-examples.git'  
   }
   stage('Code Build') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
     sh 'mvn clean compile'
    }  
   }
   stage('Unit Test') {
       withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
        sh 'mvn test'
     }  
   }
   stage('SonarQube Analysis') {
       withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
       sh 'mvn sonar:sonar \
             -Dsonar.projectKey=itrain_padman \
             -Dsonar.organization=itrainpadman1 \
             -Dsonar.host.url=https://sonarcloud.io \
             -Dsonar.login=fbc70550bbc212ffe48bf7a74b3fb769e0a37673'
       }
   } 
   stage('Archive to Jfrog') {
   } 
   stage('Docker Image') {
   } 
   stage('Deploy to Prods') {
   } 
}
