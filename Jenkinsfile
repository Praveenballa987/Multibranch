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
       stage('masterdeployment')
       {
           steps
           {
               deploy adapters: [tomcat9(credentialsId: 'new', path: '', url: 'http://172.31.41.177:8080')], contextPath: 'testapp', war: '**/*.war'
           }
       }
       stage('mastertesting')
       {
           steps
           {
               git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
               sh 'java -jar /var/lib/jenkins/workspace/DeclarativePipeline1/testing.jar'
           }
       }
       stage('masterDelivary')
       {
           steps
           {
               deploy adapters: [tomcat9(credentialsId: 'new', path: '', url: 'http://172.31.2.245:8080')], contextPath: 'prodapp', war: '**/*.war'
           }
       }
    }
}
