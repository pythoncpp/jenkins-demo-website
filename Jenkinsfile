pipeline {
    agent any
    stages {
        stage ('build docker image') {
            steps {
                sh '/usr/bin/docker image build -t pythoncpp/jenkinsdemo .'
            }
        }
        stage ('docker login') {
            steps {
                sh 'echo dckr_pat_SIVwbkzRZ01th6gh3OMDYfo88BM | /usr/bin/docker login -u pythoncpp --password-stdin'
            }
        }
        stage ('push docker image') {
            steps {
                sh '/usr/bin/docker image push pythoncpp/jenkinsdemo'
            }
        }
        stage ('reload docker service') {
            steps {
                sh '/usr/bin/docker service update --image pythoncpp/jenkinsdemo --force myservice'
            }
        }

    }
}
