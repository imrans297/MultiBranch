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
        
