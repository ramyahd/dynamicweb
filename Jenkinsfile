pipeline
{
    agent any
    
    
    
    tools{
    maven 'Maven'
    }
    
   stages{
    stage('Build')
        {
            steps{
              sh 'mvn clean install'
                 }
         }
       stage('functional test')
    {
    steps
    {
  blazeMeterTest credentialsId: '123', getJtl: true, getJunit: true, testId: '7422114.functionalApi', workspaceId: '390025'
    }
    }
       stage('performance test')
       {
           steps
           {blazeMeterTest abortJob: false, credentialsId: 'a0335198-0971-4c33-8cbd-266356d105ec', getJtl: true, getJunit: true, testId: '7422713.taurus', workspaceId: '390151'
           }
       }
   }
}

