pipeline {
	agent none
	environment {
		NPM_AUTH = credentials('npm-nexus')
		NUGET_AUTH = credentials('nuget-nexus')
	}
	stages {
		stage('Install Packages') {
			parallel {
				stage('Install NPM') {
					agent {
						label "npm"
					}
					steps {
						sh 'npm install'
					}
				}
				stage('Install Nuget') {
					agent {
						label "npm"
					}
					steps {
						sh 'nuget install'
					}
				}
			}
		}
	}
}