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
      
       stage('performance test')
       {
           steps
           {blazeMeterTest abortJob: true, credentialsId: 'blazemetre', getJtl: true, getJunit: true, testId: '7425390.taurus', workspaceId: '390580'
           }
      }
   }
}

