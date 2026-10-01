@Library('jenkinsLibs') _
pipeline {
    agent any

    stages {
        stage('docker build') {
            steps {
                script {
                    dockerLib.build(DockerfilePath: "02-primer-pipeline/Dockerfile",
                                    DockerImage: "caosbinario/homer_page:1.0.0-${BUILD_ID}",
                                    DockerContext: "02-primer-pipeline")
                }
            }
        }
        stage('docker push') {
            steps {
                script {
                    dockerLib.push(DockerImage: "caosbinario/homer_page:1.0.0-${BUILD_ID}")
                }
            }
        }
    }
}