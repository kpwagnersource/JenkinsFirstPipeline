
pipeline {
    agent {
    	label '!windows'
    }

    environment {
    	DISABLE_AUTH = 'true'
    	DB_ENGINE = 'sqlite'
    }

    stages {
    	stage('Build') {
    		steps {
    			echo "Database engine is ${DB_ENGINE}"
    			echo "DISABLE_AUTH is ${DISABLE_AUTH}"
    			echo "Build ID: ${BUILD_ID}"
    			echo "Build number: ${BUILD_NUMBER}"
    			echo "Build URL: ${BUILD_URL}"
    			echo "Executor number: ${EXECUTOR_NUMBER}"
    			
    			echo "Jenkins URL: ${JENKINS_URL}"
    			echo "Job name: ${JOB_NAME}"
    			echo "Node name: ${NODE_NAME}"
    			echo "Workspace: ${WORKSPACE}" 
    			sh 'printenv'
    		}
    	}
    }
    post {
        always {
            echo 'One way or another, I have finished'
            deleteDir() /* clean up our workspace */
        }
        success {
            echo 'I succeeded!'
            mail to: 'kyle.p.wagner@gmail.com',
            		subject: "Successful Pipeline: ${currentBuild.fullDisplayName}",
            		body "Success: ${env.BUILD_URL}"
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
        }
        changed {
            echo 'Things were different before...'
        }
    }
}