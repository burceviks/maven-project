pipeline {
    agent any
    tools { 
        maven 'maven-3' 
    }
    stages {
        stage ('Build') {
            steps {
                sh "mvn clean package"
                sh "sudo docker build . -t tomcatwebapp:${env.BUILD_ID}"
            }
            post{
                success{
                    sh ' echo "success!!! Archiving" '
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }

        stage ('Last Step') {
            steps {
                echo 'This is a minimal pipeline.'
            }
        }
    }
}
