pipeline {
     agent any
     stages {
        stage("Build") {
            steps {
                bat 'docker compose down --remove-orphans'
                bat 'docker container prune --force'
                bat 'docker image prune --force'
            }
        }
        stage("Deploy") {
            steps {
                bat 'docker compose -f docker-compose.yml up --build --no-deps --renew-anon-volumes --detach --remove-orphans'
            }
        }
    }
}
