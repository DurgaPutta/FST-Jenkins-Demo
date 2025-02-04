pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
                sh "mvn compile"
            }
        }

        stage("Test") {
            steps {
                wrap([$class: "Xvfb", debug: true, displayName: 22, displayNameOffset: 0, timeout: 10 autoDisplayName: true]) {
                    sh "mvn test"
                }
            }
        }

        stage("Publish") {
            steps {
                testNG()
            }
        }
    }
}
