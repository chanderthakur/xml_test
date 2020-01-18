node('linux_vm'){
	stage('Clean Workspace'){
		deleteDir()
	}
	stage('Checkout SCM'){
		checkout scm
	}
	stage('Run Tests'){
		sh "whoami"
		sh "pip install -r requirements.txt"
		sh "python qa_1931_decorators_wrapper.yml"
	}
	stage('Test Results'){
		//junit allowEmptyResults: true, testResults: 'test-reports/*.xml', healthScaleFactor: 0.0
		//step([$class: 'XUnitBuilder',
           // thresholds: [[$class: 'FailedThreshold', unstableThreshold: '1']],
           // tools: [[$class: 'JUnitType', pattern: 'test-reports/*.xml']
               //      ]])
          junit 'test-reports/*.xml'
	}
}


