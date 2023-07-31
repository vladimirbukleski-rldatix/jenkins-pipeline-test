pipeline {
    agent any

    stages {
        stage('Install Packages') {
            parallel {
                stage('Install NPM') {
                    agent {
                        label "npm"
                    }
                    steps {
                        sh 'npm init --yes'
                        sh 'npm install'
                    }
                }
                stage('Install Nuget') {
                    agent {
                        label "nuget"
                    }
                    steps {
                        sh 'nuget install'
                    }
                }
            }
        }
    }
}