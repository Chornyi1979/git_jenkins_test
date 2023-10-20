pipeline {
    agent any
    triggers {
        githubPush()
    }
    stages {
        stage('Clone repositorys') {
            steps {
                git branch: 'feature', url: 'https://github.com/Chornyi1979/git_jenkins.git'
            }
        }
        stage('Lint Dockerfiles') {
            steps {
                sh 'docker run --rm -i hadolint/hadolint:2.10.0 < Dockerfile'
            }
        }
    }
    post {
        failure {
            script {
                // Заблокувати можливість мержа feature гілки в основну гілку
                sh 'git push origin :refs/heads/feature'
            }
        }
    }
}
