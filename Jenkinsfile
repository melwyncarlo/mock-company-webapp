pipeline
{
    agent any
    stages
    {
        stage('Assemble/Build')
        {
            steps
            {
                echo "\n\n Assembling/building the Mock Company webapp ...\n\n"
                nodejs(nodeJSInstallationName: 'node16')
                {
                    sh '${PWD}/gradlew assemble'
                }
                echo "\n\n ... Done!\n\n"
            }
        }
        stage('Test')
        {
            steps
            {
                echo "\n\n Groovy testing the Mock Company webapp ...\n\n"
                nodejs(nodeJSInstallationName: 'node16')
                {
                    sh '${PWD}/gradlew test'
                }
                echo "\n\n ... Done!\n\n"
            }
        }
    }
}
