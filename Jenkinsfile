@Library('adop-pluggable-scm-jenkinsfile') _

pipeline {
    agent { label 'java8' }
    
    stages{
        stage("Reference Application Build"){
            steps{
                echo 'Compiling...'
                deleteDir()
                checkout scm
                withMaven(maven: 'ADOP Maven'){
                  sh "mvnw clean install"
                }
            }
        }
    }
}
