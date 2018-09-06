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
                checkout scmGet("${SCM_URL}", "${SCM_NAMESPACE}", "${repoName}", "${SCM_CREDENTIAL_ID}", 'master')
                sh "${tool name: 'sbt', type:'org.jvnet.hudson.plugins.SbtPluginBuilder$SbtInstallation'}/bin/sbt compile"
                sh "./mvnw clean install -DskipTests"
            }
        }
    }
}
