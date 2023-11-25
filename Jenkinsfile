pipeline {
    agent any
    stages {
        stage ('build docker image') {
            steps {
                sh '/usr/bin/docker image build -t <docker hub username>/jenkinsdemo .'
            }
        }
        stage ('docker login') {
            steps {
                sh 'ehcho <token> | </token>/usr/bin/docker login -u <username> --password-stdin'
            }
        }
        stage ('push docker image') {
            stpes {
                sh '/usr/bin/docker image push <username>/jenkinsdemo'
            }
        }
        stage ('reload docker service') {
            steps {
                sh '/usr/bin/docker service update --image <username>/jenkinsdemo --force myservice'
            }
        }

    }
}
