pipeline {
    agent any

    stages {
        stage("init"){
            steps{
                script {
                    git branch: 'main', credential: 'github',url: 'https://github.com/kellychoko/wordsmith-api.git'
                }
            }
        }

        stage("Build Artifact") {
            tools{
                maven "maven-3.9.3"
            }
            steps {
                script {
                    sh "mvn clean install"
                }
            }
        }

        stage("Unit Test") {
            tools {
                maven "maven-3.9.3"
            }
            steps {
                script {
                    sh "mvn test"
                }
            }
        }
    }
}
