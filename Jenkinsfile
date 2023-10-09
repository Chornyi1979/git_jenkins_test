pipeline {
    agent any
    git url: 'https://github.com/sebin-vincent/Treasure_Hunt.git',branch: 'feature'
    stages {
        stage('Clone repository') {
            steps {
                git branch: 'feature', url: 'https://github.com/Chornyi1979/git_jenkins.git'
            }
        }
        stage('Lint Dockerfiles') {
            steps {
                sh 'docker run --rm -i hadolint/hadolint:2.12.0 < Dockerfile'
            }
        }
    }
}
