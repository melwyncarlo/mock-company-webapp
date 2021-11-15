pipeline
{
    agent any
    stages
    {
        stage('Install Dependencies')
        {
            steps
            {
                sh -c 'echo -e "\n\n Downloading and installing Node Version Manager ...\n\n"'
                sh -c 'echo -e "\n\n ... Done!\n\n"'
            }
        }
        stage('Assemble/Build')
        {
            steps
            {
                sh -c 'echo -e "\n\n Assembling/building the Mock Company webapp ...\n\n"'
                sh -c './gradlew assemble'
                sh -c 'echo -e "\n\n ... Done!\n\n"'
            }
        }
        stage('Test')
        {
            steps
            {
                sh -c 'echo -e "\n\n Groovy testing the Mock Company webapp ...\n\n"'
                sh -c './gradlew test'
                sh -c 'echo -e "\n\n ... Done!\n\n"'
            }
        }
    }
}
