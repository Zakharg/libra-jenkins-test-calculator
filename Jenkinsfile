pipeline {
    agent any 

    stages {
        stage ('Compile stage') {
            steps {
            	node{
	            	    withMaven(maven : 'Maven 3.5.0', globalMavenSettingsConfig: "GlobalMavenSettings.xml.20171122") {
	                    	sh 'mvn clean install'
	                }
            	}
            }
        }
        
        stage ('Deployment Stage') {
            steps {
            	node{
	            	    withMaven(maven : 'Maven 3.5.0', globalMavenSettingsConfig: "GlobalMavenSettings.xml.20171122") {
	                    sh 'mvn deploy'
	                }
            	}
            }
        }
    }

}