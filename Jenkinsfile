// Instead of annotating an unnecessary import statement, the symbol _ is annotated, according to the annotation pattern.
@Library('adop-pluggable-scm-jenkinsfile') _

def repoName = "scala-maven-template-master"
def regRepo = "adop-cartridge-scala-regression-tests"

pipeline {
    agent { label 'java8' }
    environment{
        // Sonar Project Info - You must replace these vars with the Project Name and Key from the ADOP Portal!
        SONAR_PROJECT_NAME = 'Simple Scala project analyzed with the SonarQube Runner'
        SONAR_PROJECT_KEY = 'scala-sonar-runner-simple'
        ENVIRONMENT_NAME = 'CI'
        }
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
