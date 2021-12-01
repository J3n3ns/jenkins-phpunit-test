pipeline {
	agent {
		docker {
			image 'composer:latest'
		}
	}
	stages {
		stage('Builds') {
			steps {
				sh 'composer install'
			}
		}
		stage('Tests') {
			steps {
                sh './vendor/bin/phpunit tests'
            }
		}
	}
}