pipeline
{
    agent any
    stages
    {
        stage('Install Dependencies')
        {
            steps
            {
                sh 'echo -e "\n\n Downloading and installing Node Version Manager ...\n\n"'
                sh 'wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh'
                sh '${PWD}/install.sh'
                sh 'echo -e "\n\n ... Done!\n\n"'
                
                sh 'echo -e "\n\n Installing and using LTS NodeJS ...\n\n"'
                sh 'nvm install --lts'
                sh 'nvm use --lts'
                sh 'echo -e "\n\n ... Done!\n\n"'
            }
        }
        stage('Assemble/Build')
        {
            steps
            {
                sh 'echo -e "\n\n Assembling/building the Mock Company webapp ...\n\n"'
                sh '${PWD}/gradlew assemble'
                sh 'echo -e "\n\n ... Done!\n\n"'
            }
        }
        stage('Test')
        {
            steps
            {
                sh 'echo -e "\n\n Groovy testing the Mock Company webapp ...\n\n"'
                sh '${PWD}/gradlew test'
                sh 'echo -e "\n\n ... Done!\n\n"'
            }
        }
    }
}
