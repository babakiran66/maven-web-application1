node ('master')
 {
  
  def mavenHome = tool name: "maven-3.6.1"
  
      echo "GitHub BranhName ${env.BRANCH_NAME}"
      echo "Jenkins Job Number ${env.BUILD_NUMBER}"
      echo "Jenkins Node Name ${env.NODE_NAME}"
  
      echo "Jenkins Home ${env.JENKINS_HOME}"
      echo "Jenkins URL ${env.JENKINS_URL}"
      echo "JOB Name ${env.JOB_NAME}"
  
   //properties([[$class: 'JiraProjectProperty'], buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '2', daysToKeepStr: '', numToKeepStr: '2')), pipelineTriggers([pollSCM('* * * * *')])])
  
  stage("CheckOutCodeGit")
  {
   git branch: 'master', credentialsId: 'c7c9ec35-23f2-4f25-9c52-86cf778ebb3c', url: 'https://github.com/babakiran66/maven-web-application1.git'
   
 }
 
 stage("Build")
 {
 sh "${mavenHome}/bin/mvn clean package"
 }
 
 withCredentials([string(credentialsId: '1d9ae8fc-a423-433d-949c-20ab584bfa14', variable: 'Dockerhubpassword')]) {
    // some block
}
