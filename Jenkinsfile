pipeline
{
    agent any
    stages
    {
        stage('continous Download')
        {
            steps
            {
                git 'https://github.com/imrans297/Maven.git'
            }
        }
        stage('Cont_Build')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('Cont_Deployment')
        {
            steps
            {
                sh 'scp /var/lib/jenkins/workspace/DeclerativePipelineTesting/webapp/target/webapp.war ubuntu@172.31.14.48:/var/lib/tomcat9/webapps/testapp1.war'
            }
        }
        stage('Cont_Testing')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
                sh 'java -jar /var/lib/jenkins/workspace/DeclerativePipelineTesting/testing.jar'
            }
        }
        stage('cont_Delivery')
        {
            steps
            {
                sh 'scp /var/lib/jenkins/workspace/DeclerativePipelineTesting/webapp/target/webapp.war ubuntu@172.31.4.138:/var/lib/tomcat9/webapps/prodapp1.war'
            }
        }
    }
}
