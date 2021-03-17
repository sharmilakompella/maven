node('master') 
{
    stage('ContinuousDownload_PB')
    {
       git 'https://github.com/sharmilakompella/Maven.git'
    }
    stage('ContinuousBuild_Master')
    {
       sh 'mvn package'
    }
    stage('ContinuousDeployment_PB')
    {
     sh 'scp /home/ubuntu/.jenkins/workspace/Pipeline_SCM/webapp/target/webapp.war ubuntu@172.31.1.245:/var/lib/tomcat9/webapps/qaapp.war'  
	            
		 
    }
    stage('ContinuousTesting_PB')
    {
       git 'https://github.com/sharmilakompella/Testing.git'
	                                        
       sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline/testing.jar'
	                                
    }
    
}
