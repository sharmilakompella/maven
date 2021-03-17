node('master') 
{
    stage('ContinuousDownload_Loans')
    {
       git 'https://github.com/sharmilakompella/Maven.git'
    }
    stage('ContinuousBuild_Loans')
    {
       sh 'mvn package'
    }
    
}
