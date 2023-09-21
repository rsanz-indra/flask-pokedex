pipeline {
    agent any
    environment{
        DOCKERHUB_CREDENCIALS = credentials ('dockerhub')
        RepoDockerHub = 'rasanvil'
        NameContainer = 'pokedex-flask'
    }

    stages {
         stage('Echo'){
             steps{
                sh "echo $DOCKERHUB_CREDENCIALS_USR / $DOCKERHUB_CREDENCIALS_PSW"
            }
         }
        
       
    }
}
