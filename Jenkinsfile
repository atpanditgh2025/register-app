pipeline {
    agent { label 'devopsbuildsrv1' }
    tools {
        jdk 'Java17'
        maven 'maven3'
    }
	
    stages{
        stage("Cleanup Workspace"){
                steps {
                cleanWs()
                }
        }

        stage("Checkout from SCM"){
                steps {
                    git branch: 'main', credentialsId: 'github', url: 'https://github.com/atpanditgh2025/register-app'
                }
        }

        stage("Build Application"){
            steps {
                sh "mvn clean package"
            }

       }
    }
}
