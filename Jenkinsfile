pipeline
{
    agent any
    stages
    {
        stage('masterdownload')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/maven.git'
            }
    
        }
        stage('masterbuild')
        {
            steps
            {
                sh 'mvn package'
            }
        }
    }
}    
