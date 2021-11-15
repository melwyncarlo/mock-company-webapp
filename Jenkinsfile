pipeline
{
    agent any
    stages
    {
        stage('Install Dependencies')
        {
            steps
            {
                sh 'echo "\n\n Downloading and installing Node Version Manager ...\n\n"'
                sh 'wget https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh'
                sh '${PWD}/install.sh'
                sh 'echo "\n\n ... Done!\n\n"'
                
                sh 'echo "\n\n Installing and using LTS NodeJS ...\n\n"'
                sh 'nvm install --lts'
                sh 'nvm use --lts'
                sh 'echo "\n\n ... Done!\n\n"'
            }
        }
        stage('Assemble/Build')
        {
            steps
            {
                sh 'echo "\n\n Assembling/building the Mock Company webapp ...\n\n"'
                sh '${PWD}/gradlew assemble'
                sh 'echo "\n\n ... Done!\n\n"'
            }
        }
        stage('Test')
        {
            steps
            {
                sh 'echo "\n\n Groovy testing the Mock Company webapp ...\n\n"'
                sh '${PWD}/gradlew test'
                sh 'echo "\n\n ... Done!\n\n"'
            }
        }
    }
}
