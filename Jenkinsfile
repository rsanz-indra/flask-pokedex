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
               sh "echo $DOCKERHUB_CREDENCIALS_PSW | docker login -u $DOCKERHUB_CREDENCIALS_USR --password-stdin "
            }
        }
        
       
    }
}
