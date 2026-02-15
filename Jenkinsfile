@Library('Shared')_
pipeline{
    agent { label 'vinod'}
    
    stages{
        stage("Code clone"){
            steps{
                sh "whoami"
                sh "cloning repo now"
                git branch: 'main', url: 'https://github.com/adnan-sharief/django-notes-app'
            }
        }
        stage("Code Build"){
            steps{
                sh "building docker image now"
                sh "docker build -t notes-app:latest ."
            }
        }
        stage("Push to DockerHub"){
            steps{
                sh "pushing to dockerhub now"
                dockerpush("dockerHubCreds","notes-app","latest")
            }
        }
        stage("Deploy"){
            steps{
                sh "deploying now"
                deploy()
            }
        }
        
    }
}
