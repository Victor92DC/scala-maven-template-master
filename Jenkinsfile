@Library('adop-pluggable-scm-jenkinsfile') _

def repoName = "scala-maven-template-master"
def regRepo = "adop-cartridge-scala-regression-tests"

pipeline {
    agent { label 'java8' }
    
    stages{
        stage("Reference Application Build"){
            steps{
                echo 'Scala Application pipeline.'
                deleteDir()
                checkout scm
                sh "./mvnw clean install -DskipTests"
            }
        }
    }
}
