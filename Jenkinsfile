pipeline {
    agent any
     stages {
        stage('Restore packages'){
           steps{
                  bat 'dotnet restore WebApplication1.sln'
               git credentialsId: '0358e590-33d7-4e1e-9977-39ebe9b4a870', url: 'https://github.com/pranjalpg/WebApplication1.git' }
         }
        stage('Clean'){
           steps{
               bat 'dotnet clean WebApplication1.sln --configuration Release'
            }
         }
        stage('Build'){
           steps{
               bat 'dotnet build WebApplication1.sln --configuration Release --no-restore'
            }
         }
        stage('Publish'){
             steps{
               bat 'dotnet publish WebApplication1/WebApplication1.csproj --configuration Release --no-restore'
             }}
     }
}
