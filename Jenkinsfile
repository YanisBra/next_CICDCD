pipeline {
    agent {
        label 'JenkinsAgent_next_docker'
    }

    stages {
        stage('Continuous Integration') {
            steps {
                git branch: 'main', url: 'https://github.com/YanisBra/next_CICDCD.git'
            }
        }
        stage('Continuous Delivery') {
            steps {
                sh 'npm install'
                sh 'docker build . -t yanisbra/next_cicdcd'
                sh "docker login -u yanisbra -p ${DOCKER_PASSWORD}"
                sh 'docker push yanis/next_cicdcd'
            }
        }
    }
}
