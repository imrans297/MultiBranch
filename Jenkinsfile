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
                sh 'scp /var/lib/jenkins/workspace/MultiBranchPipeline/webapp/target/webapp.war ubuntu@172.31.82.132:/var/lib/tomcat9/webapps/testapp21.war'
            }
        }
        stage('Cont_Testing_Master')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
                sh 'java -jar /var/lib/jenkins/workspace/MultiBranchPipeline/testing.jar'
            }
        }
        stage('cont_Delivery_Master')
        {
            steps
            {
                sh 'scp /var/lib/jenkins/workspace/MultiBranchPipeline/webapp/target/webapp.war ubuntu@172.31.80.107:/var/lib/tomcat9/webapps/prodapp21.war'
            }
        }
    }
}
