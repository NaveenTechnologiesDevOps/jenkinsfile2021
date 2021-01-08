node('master')
{
    properties([[$class: 'JiraProjectProperty'], buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '3', daysToKeepStr: '', numToKeepStr: '3')), pipelineTriggers([pollSCM('* * * * *')])])

    def mavenHome = tool name: "maven3.6.3"
    mavenHome="$mavenHome/bin"
    
    stage("CheckoutCode")
    {
    git branch: 'development', credentialsId: '47bb3ee0-921a-4468-b969-c29cb31a067a', url: 'https://github.com/NaveenTechnologiesDevOps/maven-web-application.git'
    }
    stage("Build")
    {
    sh "${mavenHome}/mvn clean package"
    }
    /*
    stage("SonarQubeReportExecution")
    {
    sh "${mavenHome}/mvn sonar:sonar"
    }
    stage("UploadArtifactIntoNexus")
    {
    sh "${mavenHome}/mvn deploy"
    }
    stage("DeployAppIntoTomcatServer")
    {
        sshagent(['2c80e4db-6a78-4b4b-97b3-366aed7c6f4a']) {
        sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.126.253.40:/opt/apache-tomcat-9.0.41/webapps/"
        }  
    }
    stage("EmailNotification")
    {
        mail bcc: 'Naveenleo91@gmail.com', body: '''Build Over

        Regards,
        NaveenTechnologies,
        9738632375''', cc: 'Naveenleo91@gmail.com', from: '', replyTo: '', subject: 'Build Over', to: 'Naveenleo91@gmail.com'
    }
    */
}
