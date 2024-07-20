pipeline {
	agent {
		docker {
			image: docker:24.0.5
			services:
    				- name: registry.hub.docker.com/library/docker:24.0.5-dind
      				alias: docker
		}
	}
	stages {
		stage('Build') {
			steps {
				sh 'composer install'
			}
		}
		stage('Test') {
			steps {
                sh './vendor/bin/phpunit tests'
            }
		}
	}
}