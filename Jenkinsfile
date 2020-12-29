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
		stage ('Code Quality Stage'){
			steps {
			        echo 'Running  Code Quality Stage'
			}
		}
	}
}
