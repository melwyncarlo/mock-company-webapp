pipeline
{
    agent any
    stages
    {
        stage('Install Dependencies')
        {
            steps
            {
                echo "\n\n Downloading and installing Node Version Manager ...\n\n"
                sh 'rm -rf ${HOME}/.nvm'
                sh 'wget https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh'
                sh 'sudo chmod +x ${PWD}/install.sh'
                sh '${PWD}/install.sh'
                echo "\n\n ... Done!\n\n"
                
                echo "\n\n Installing and using LTS NodeJS ...\n\n"
                sh 'sudo chmod +x ${HOME}/.nvm/nvm.sh'
                sleep 10
                sh '${HOME}/.nvm/nvm.sh install --lts'
                sleep 10
                sh '${HOME}/.nvm/nvm.sh use --lts'
                sleep 10
                echo "\n\n ... Done!\n\n"
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
