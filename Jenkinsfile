@Library('adop-pluggable-scm-jenkinsfile') _

pipeline {
    agent { label 'java8' }
    
    stages{
        stage("Reference Application Build"){
            steps{
                echo 'Compiling...'
                deleteDir()
                checkout scm
                sh "${tool name: 'sbt', type:'org.jvnet.hudson.plugins.SbtPluginBuilder$SbtInstallation'}/bin/sbt compile"
            }
        }
    }
}
