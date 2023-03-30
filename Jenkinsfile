pipeline
{
    agent any
    stages
    {
        stage('continous Download_Master')
        {
            steps
            {
                git 'https://github.com/imrans297/Maven.git'
            }
        }
        stage('Cont_Build_Master')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('Cont_Deployment_Master')
        {
            steps
            {
                sh 'scp /var/lib/jenkins/workspace/DeclerativePipelineTesting/webapp/target/webapp.war ubuntu@172.31.14.48:/var/lib/tomcat9/webapps/testapp1.war'
            }
        }
        stage('Cont_Testing_Master')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
                sh 'java -jar /var/lib/jenkins/workspace/DeclerativePipelineTesting/testing.jar'
            }
        }
        stage('cont_Delivery_Master')
        {
            steps
            {
                sh 'scp /var/lib/jenkins/workspace/DeclerativePipelineTesting/webapp/target/webapp.war ubuntu@172.31.4.138:/var/lib/tomcat9/webapps/prodapp1.war'
            }
        }
    }
}
