pipeline
{
    agent any
    stages
    {
        stage('continous Download_Loans')
        {
            steps
            {
                git 'https://github.com/imrans297/Maven.git'
            }
        }
        stage('Cont_Build_loans')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('Cont_Deployment_Loans')
        {
            steps
            {
                sh 'scp /var/lib/jenkins/workspace/MultiBranchPipeline/webapp/target/webapp.war ubuntu@172.31.82.132:/var/lib/tomcat9/webapps/testapp1.war'
            }
        }
    }
}
