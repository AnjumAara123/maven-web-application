#!groovy
properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '3'))])


node('master'){
   cleanWs notFailBuild: true
   
 stage('Chekout the code')   {
    git branch: 'development', credentialsId: 'd2acdaf0-3e1a-435b-bd20-d7eeb31a7a56', url: 'https://github.com/syedmdwaris/maven-web-application.git' 
 }
 
 
 stage('Run Unit Test cases'){
     if(isUnix()){
      sh 'mvn test'
     }
     else{
        bat 'mvn test' 
     }
 }
 stage('build'){
     if(isUnix()){
      sh 'mvn clean package'
     }
     else{
        bat 'mvn clean package' 
     }
 }
 
 /* stage('SonarQube Report'){
     if(isUnix()){
      sh 'mvn sonar:sonar'
     }
     else{
        bat 'mvn sonar:sonar' 
     }
 }
 
 stage('Upload Artifacts'){
     if(isUnix()){
      sh 'mvn deploy'
     }
     else{
        bat 'mvn deploy' 
     }
 }
 */
 stage('Deploy into Tomcat Server'){
      
     sh 'echo "Deploymnet started SYED WARIS"'
     sh 'cp $WORKSPACE/target/*.war /opt/apache-tomcat-9.0.14/webapps/'
     sh 'echo "deployment over SYED MD WARIS"'
      
        
    }
    
   /* stage('Notification'){
      mail bcc: 'devopstrainingblr@gmail.com', body: '''Buid Done

Regards,
Mithun Technologies.''', cc: 'devopstrainingblr@gmail.com', from: '', replyTo: '', subject: 'Using Pipeline Script Email Notification', to: 'devopstrainingblr@gmail.com'  
        
    }
    
    */
}
