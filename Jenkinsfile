pipeline {
    agent any
    stages {
        stage('Checkout project') {
            steps {
                checkout scm
                cleanWs()
            }
        }
        stage('Checkout ansible') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'IgnoreNotifyCommit'], [$class: 'SparseCheckoutPaths', sparseCheckoutPaths: [[path: 'HelloWorld']]]], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/andre-d-gomes/CalculatorLibrary.git']]])
                sh 'ls -la'
            }
        }
        stage('Build and Tests') {
            steps {
                echo 'Build and Tests'
            }
        }
    }
}