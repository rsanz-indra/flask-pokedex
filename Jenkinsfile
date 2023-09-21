pipeline {
    agent any
    environment{
        DOCKERHUB_CREDENCIALS = credentials ('dockerhub')
        RepoDockerHub = 'rasanvil'
        NameContainer = 'pokedex-flask'
    }

    stages {
        stage('Build'){
            steps{
                sh "docker build -t ${env.RepoDockerHub}/${env.NameContainer}:${env.BUILD_NUMBER} ."
            }
        }

        stage('Login to Dockerhub'){
            steps{
                sh "docker login -u rasanvil -p Chiquito99 "
            }
        }

        stage('Push image to Dockerhub'){
            steps{
                sh "docker push ${env.RepoDockerHub}/${env.NameContainer}:${env.BUILD_NUMBER} "
            }
        }

        stage('Deploy container'){
            steps{
                sh "if [ 'docker stop ${env.NameContainer}' ] ; then docker rm -f ${env.NameContainer} && docker run -d --name ${env.NameContainer} -p 5000:5000 ${env.RepoDockerHub}/${env.NameContainer}:${env.BUILD_NUMBER} ; else docker run -d --name pokedex-flask -p 5000:5000 ${env.RepoDockerHub}/${env.NameContainer}:${env.BUILD_NUMBER} ; fi"
            }
        }
        
        stage('Docker logout'){
            steps{
                sh "docker logout"
            }
        }
    }
}
