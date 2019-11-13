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
           {
               blazeMeterTest abortJob: true, credentialsId: 'e49d3c9f-0b7c-40e5-a305-7c37986d0ecf', getJtl: true, getJunit: true, testId: '7422528.taurus', workspaceId: '390151'
           }
      }
   }
}

