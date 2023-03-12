pipeline {
    agent { label 'docker' }
    triggers { 
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/Bharatkumar5690/StudentCoursesRestAPI.git',
                    branch: 'develop'
            }
        }
        stage('build') {
            steps {
                sh 'docker image build -t bharatnar/src:latest .'
            }
        }
        stage('scan and push') {
            steps {
                sh 'echo docker scan bharatnar/src:latest'
                sh 'docker image push bharatnar/src:latest'
            }
        }
    }

}