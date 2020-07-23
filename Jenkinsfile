pipeline {
	agent none
	stages {
	    stage('Maven Build') {
	     agent {
       		 docker {
            image 'maven:3-alpine'
            args '-v /root/.m2:/root/.m2'
        }
	}
   		steps {
   	       		sh 'mvn clean install -DskipTests=true'
   	    	}
    	}
    	stage('Docker Build') {
    	agent any
    		steps{
    		    sh 'docker build -t pratyay/space-management-system:latest .'
    		}
    	}
    	
	
	}
}
