
properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '4'))])

node{
    
  stage('Checkout the code') 
    {
     git branch: 'development', credentialsId: '21c9fb87-4015-488a-a873-9959bd89a226', url: 'https://github.com/syedmdwaris/maven-web-application.git'  
    }
    
   
    stage('Run Unit Test cases')
    {
      if(isUnix()){
       sh  'mvn test'
        }
        else{
           bat  'mvn test' 
        }
    }
    
    
    stage('Create Package')
    {
      if(isUnix()){
       sh  'mvn clean package'
        }
        else{
           bat  'mvn clean package' 
        }
    }
      /*
    stage('SonarQube Report')
    {
      if(isUnix()){
       sh  'mvn sonar:sonar'
        }
        else{
           bat  'mvn sonar:sonart' 
        }
    }
    stage('Upload artifact into Nexus')
    {
      if(isUnix()){
       sh  'mvn deploy'
        }
        else{
           bat  'mvn deploy' 
        }
    }
    
    stage('Deploy app into Tomcat Server')
    {
      sh 'echo "App Deploymemt started"'  
      sh  'cp $WORKSPACE/target/*.war  /Users/mithunreddy/MithunTechnologies/Softwares/Running/apache-tomcat-9.0.13/webapps/'
      sh  'echo App deployed successfully'

    }
    
    stage('Send Notifications')
    {
        
      mail bcc: 'devopstrainingblr@gmail.com', body: '''Build Done.
Regards,
Mithun Technologies.
''', cc: 'devopstrainingblr@gmail.com', from: '', replyTo: '', subject: 'Build Done', to: 'devopstrainingblr@gmail.com'
  
    } */
    
}
