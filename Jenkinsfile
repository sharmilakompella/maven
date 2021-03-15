node('master') 
{
    stage('ContinuousDownload')
    {
       git 'https://github.com/sharmilakompella/Maven.git'
    }
    stage('ContinuousBuild')
    {
       sh 'mvn package'
    }
    stage('ContinuousDeployment')
    {
     sh 'scp /home/ubuntu/.jenkins/workspace/Pipeline_SCM/webapp/target/webapp.war ubuntu@ 172.31.1.245:/var/lib/tomcat9/webapps/qaapp.war'  
	            
		 
    }
    stage('ContinuousTesting')
    {
       git 'https://github.com/sharmilakompella/Testing.git'
	                                        
       sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline/testing.jar'
	                                
    }
    stage('ContinuousDelivery')
    {
        sh 'scp /home/ubuntu/.jenkins/workspace/Pipeline_SCM/webapp/target/webapp.war ubuntu@172.31.5.169:/var/lib/tomcat9/webapps/prodapp.war'   
    }
    
}
