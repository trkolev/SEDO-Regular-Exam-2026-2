pipeline{
    agent any
    stages{
        stage('Restore'){
            when {
                expression {
                    return env.GIT_BRANCH == 'origin/main'
                }
            }
            steps{
                echo 'Restoring...'
                bat 'dotnet restore'
            }
        }
        stage('Build'){
            when {
                expression {
                    return env.GIT_BRANCH == 'origin/main'
                }
            }
            steps{
                echo 'Building...'
                bat 'dotnet build -no-restore'
            }
        }
        stage('Test'){
            when {
                expression {
                    return env.GIT_BRANCH == 'origin/main'
                }
            }
            steps{
                echo 'Testing...'
                bat 'dotnet test -no-build --verbosity normal'
            }
        }
    }
}