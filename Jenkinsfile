pipeline {
    agent any
    stages{
          stage('SCM Checkout'){
     git 'https://github.com/burceviks/maven-project'
                               }
        stage('Build'){
            steps{
            def mvnHome =  tool name: 'maven-3', type: 'maven'
              sh "${mvnHome}/bin/mvn clean package"
            }
        }
    }
}
