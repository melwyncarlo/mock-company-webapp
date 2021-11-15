pipeline
{
    agent any
    stages
    {
        stage('Install Dependencies')
        {
            steps
            {
                sh 'wget https://raw.githubusercontent.com/creationix/nvm/v0.35.3/install.sh && bash install.sh'
                sh '. ~/.nvm/nvm.sh'
                sh '. ~/.profile'
                sh '. ~/.bashrc'
                sh 'nvm install --lts'
                sh 'nvm use --lts'
                sh 'node -v'
            }
        }
        stage('Assemble/Build')
        {
            steps
            {
                echo "\n\n Assembling/building the Mock Company webapp ...\n\n"
                sh '${PWD}/gradlew assemble'
                echo "\n\n ... Done!\n\n"
            }
        }
        stage('Test')
        {
            steps
            {
                echo "\n\n Groovy testing the Mock Company webapp ...\n\n"
                sh '${PWD}/gradlew test'
                echo "\n\n ... Done!\n\n"
            }
        }
    }
}
