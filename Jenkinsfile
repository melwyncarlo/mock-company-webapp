pipeline
{
    agent any
    stages
    {
        stage('Install Dependencies')
        {
            steps
            {
                sh -c 'echo -e "\n\n Installing Node Version Manager ...\n\n"'
                sh -c 'wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash'
                sh -c 'echo -e "\n\n ... Done!\n\n"'
                
                sh -c 'echo -e "\n\n Installing and using LTS NodeJS ...\n\n"'
                sh -c 'nvm install --lts'
                sh -c 'nvm use --lts'
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
