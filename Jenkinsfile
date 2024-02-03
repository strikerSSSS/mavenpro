pipeline {
    agent any

    stages {
        stage('clone from github(GitHubBuild)') {
            steps {
                git branch: 'master', url: 'https://github.com/adikesavanaidug2404/DeployProject.git'
            }
        }
        stage('build war file(MavenBuild)') {
            steps {
                sh "mvn clean install package"
            }
        }
    }
}
