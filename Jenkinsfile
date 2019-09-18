
pipeline {
    agent {
    	docker { image 'node:7-alphine'}
    }
    stages {
    	stage('Test') {
    		steps {
    			sh 'node --version'
    		}
    	}
    }