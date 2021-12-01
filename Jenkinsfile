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
                sh '.vendor/bin.phpunit --log-junit ;pgs/unitreport.xml -c tests/phpunit.xml tests'
                // sh './vendor/bin/phpunit tests'
            }
		}
	}
	post {
		always {
			junit testResults: 'logs/unitreport.xml'
		}
	}
}