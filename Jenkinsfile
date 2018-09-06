@Library('adop-pluggable-scm-jenkinsfile') _

pipeline {
    agent { label 'java8' }
    
    stages{
        stage("Reference Application Build"){
            steps{
                echo 'Compiling...'
                deleteDir()
                checkout scm
                sh "./mvnw clean install -DskipTests"
            }
        }
    }
}
