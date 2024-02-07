pipeline {
    agent any
    environment {
        SONARQUBE_HOME = tool 'sonarpro'
    }


    stages {
        stage('clone from github(GitHubBuild)') {
            steps {
                git branch: 'master', url: 'https://github.com/strikerSSSS/mavenpro.git'
            }
        }
        stage('build war file(MavenBuild)') {
            steps {
                sh "mvn clean install package"
            }
        }
        stage('SonarQube Analysis') {
            steps {
                script {
                    withSonarQubeEnv('sonarcube') {
                        sh "${SONARQUBE_HOME}/bin/sonar-scanner -Dsonar.projectKey=EKART -Dsonar.projectName=EKART -Dsonar.java.binaries=."
                    }
                }
            }
        }
    }
}
    
