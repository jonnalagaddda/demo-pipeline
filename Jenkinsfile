pipeline {
	agent any
	stages {
		stage ('Git Checkout') {
			steps{
				git branch: 'main', url: 'https://github.com/jonnalagaddda/demo-pipeline.git'
			}
		}
		stage ('Build'){
			steps {
			        echo 'Running Build Stage'
			}
		}
		stage ('Code Quality'){
			steps {
			        echo 'Running  Code Quality Stage'
			}
		}
		stage ('Nexus Upload'){
			steps {
			        echo 'Running  Nexus Upload Stage'
			}
		}
		stage ('Dev Deploy'){
			steps {
			        echo 'Running  Dev Deploy Stage'
			}
		}
		stage ('Dev Approval'){
			steps {
			        echo "Taking approval from DEV Manager for QA Deployment"
                    timeout(time: 7, unit: 'DAYS') {
                    input message: 'Do you want to deploy?', submitter: 'admin'
					}
				}
			}
		stage ('Qa Deploy'){
			steps {
			        echo 'Running  Qa Deploy Stage'
			}
		}
		stage ('Qa Approval'){
			steps {
			        echo 'Running  Qa Approval Stage'
					echo "Taking approval from QA manager"
                    timeout(time: 7, unit: 'DAYS') {
                    input message: 'Do you want to proceed to PROD?', submitter: 'admin,manager_userid'
					}
				}
			}
		stage ('Prod Deploy '){
			steps {
			        echo 'Running  Prod Deployl Stage'
			}
		}
	}
}
