pipeline
{
    agent any
    stages
    {
        stage('Assemble/Build')
        {
            steps
            {
                sh 'echo -e "\n\n Assembling/building the Mock Company webapp ...\n\n"'
                sh './gradlew assemble'
                sh 'echo -e "\n\n Done!\n\n"'
            }
        }
        stage('Test')
        {
            steps
            {
                sh 'echo -e "\n\n Testing the Mock Company webapp ...\n\n"'
                sh './gradlew test'
                sh 'echo -e "\n\n Done!\n\n"'
            }
        }
    }
}
