pipeline {
    agent any
    environment{
        DOCKERHUB_CREDENCIALS = credentials ('dockerhub')
        RepoDockerHub = 'rasanvil'
        NameContainer = 'pokedex-flask'
    }

    stages {
        
         stage('Login to Dockerhub'){
            steps{
                sh "docker login -u rasanvil -p Chiquito99 "
            }
        }
        
       
    }
}
