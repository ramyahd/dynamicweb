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
   blazeMeterTest credentialsId: '123', getJtl: true, getJunit: true, testId: '7422490.functionalApi', workspaceId: '390025'
    }
    }
       stage('performance test')
       {
           steps
           {blazeMeterTest abortJob: true, credentialsId: 'blazemetre', getJtl: true, getJunit: true, testId: '7425390.taurus', workspaceId: '390580'
           }
      }
   }
}

