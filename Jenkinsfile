pipeline {
     agent any
     stages {
        stage("Build") {
            steps {
                bat "sudo docker compose down --remove-orphans"
                bat "sudo docker container prune --force"
                bat "sudo docker image prune --force"
            }
        }
        stage("Deploy") {
            steps {
                bat "sudo docker compose -f docker-compose.yml up --build --no-deps --renew-anon-volumes --detach --remove-orphans"
            }
        }
    }
}
