pipeline {
    agent any
    stages {
        stage ('build docker image') {
            steps {
                sh '/usr/bin/docker image build -t akshayrajodiya/jenkinsdemo .'
            }
        }
        stage ('docker login') {
            steps {
                sh 'echo dckr_pat_2pbRSykxKBImSXToCai7qONAxxA | /usr/bin/docker login -u akshayrajodiya --password-stdin'
            }
        }
        stage ('push docker image') {
            steps {
                sh '/usr/bin/docker image push akshayrajodiya/jenkinsdemo'
            }
        }
        stage ('reload docker service') {
            steps {
                sh '/usr/bin/docker service update --image akshayrajodiya/jenkinsdemo --force myservice'
            }
        }

    }
}