pipeline {
    agent any	
    stages {
	    stage('Scm Checkout') {
		    steps {
			    checkout scm
		    }
	    }
	     stage('SonarQube analysis') {
        	steps{
        		withSonarQubeEnv('sonarqube-9.6') { 
              			sh '''
                    sonar-scanner   -Dsonar.projectKey=php   -Dsonar.sources=.   -Dsonar.host.url=http://34.100.160.206:9000   -Dsonar.php.tests.reportPath=build/phpunit.xml -Dsonar.php.coverage.reportPaths=build/coverage.xml  -Dsonar.login=sqp_4e4b553eeca4e5e01689ad960c14c72b4b94b199 -X
                    '''
    			}
        	}
        }
    }
}
