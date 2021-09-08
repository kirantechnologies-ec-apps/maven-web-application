node ('master')
{
  def mavenHome = tool name: "maven 3.8.2"
  properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])
  
  stage ('CheckCode')
  {
    git branch: 'development', credentialsId: '815e2b99-7f93-4b5f-90f9-e5f5df8296a8', url: 'https://github.com/kirantechnologies-ec-apps/maven-web-application.git'
  }
  stage ('Build')
  {
  sh "${mavenHome}/bin/mvn clean package"
  }
  /*
  stage ('ExcuteSonarQubeReport')
  {
   sh "${mavenHome}/bin/mvn sonar:sonar"
  }
  stage ('UploadArtifactIntoNexus')
  {
  sh "${mavenHome}/bin/mvn deploy"
  }
  Stage ('DeployAppIntoTomcat')
  {
  sshagent(['49a3b151-92bf-4133-8183-6df5e323fea7'])   
  {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.235.244.65:/opt/apache-tomcat-10.0.10/webapps/"
  }
  }
  stage ('SendEmailNotification')
  {
  mail bcc: '', body: '''Build over

    With Regards
    Kiran technologies
    9866887476..
    ''', cc: 'kiranberi07@gmail.com', from: '', replyTo: '', subject: 'Build Over', to: 'kiranberi701@gmail.com'
  }
  */
}
