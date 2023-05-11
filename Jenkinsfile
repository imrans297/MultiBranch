pipeline
{
    agent any
    stages
    {
        stage('Cont-Download')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/maven.git'
            }
        }
        stage('Cont-Build')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('Cont-Deployment')
        {
            steps
            {
                sh 'scp /var/lib/jenkins/workspace/declerative-pipeline1/webapp/target/webapp.war ubuntu@172.31.82.132:/var/lib/tomcat9/webapps/test12.war'
            }
        }
        stage('Cont-Testing')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
                sh 'java -jar /var/lib/jenkins/workspace/declerative-pipeline1/testing.jar'
            }
        }
    }    
    post
    {
        success
        {
            input message: 'Need approval of DM', submitter: 'Hari'
            sh 'scp /var/lib/jenkins/workspace/declerative-pipeline1/webapp/target/webapp.war ubuntu@172.31.80.107:/var/lib/tomcat9/webapps/prodapp12.war'
        }
        failure
        {
            mail bcc: '', body: 'the jenkins CI-CD fails look into it as soon as possible', cc: '', from: '', replyTo: '', subject: 'Jenkins CI-CD fails', to: 'imrans297@outlook.com'
        }
    }
}
