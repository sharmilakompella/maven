node('master') 
{
    stage('ContinuousDownload_Master')
    {
       git 'https://github.com/sharmilakompella/Maven.git'
    }
    stage('ContinuousBuild_Master')
    {
       sh 'mvn package'
    }
    stage('ContinuousDeployment_Master')
    {
     sh 'scp /home/ubuntu/.jenkins/workspace/Pipeline_SCM/webapp/target/webapp.war ubuntu@172.31.1.245:/var/lib/tomcat9/webapps/qaapp.war'  
	            
		 
    }
    stage('ContinuousTesting_Master')
    {
       git 'https://github.com/sharmilakompella/Testing.git'
	                                        
       sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline/testing.jar'
	                                
    }
    stage('ContinuousDelivery_Master')
    {
        sh 'scp /home/ubuntu/.jenkins/workspace/Pipeline_SCM/webapp/target/webapp.war ubuntu@172.31.5.169:/var/lib/tomcat9/webapps/prodapp.war'   
    }
    
}
