pipeline
{
    agent any
    stages
    {
        stage('Assemble/Build')
        {
            steps
            {
                ./gradlew assemble
            }
        }
        stage('Test')
        {
            steps
            {
                ./gradlew test
            }
        }
    }
}
