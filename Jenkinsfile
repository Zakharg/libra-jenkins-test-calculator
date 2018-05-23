pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
				withMaven(maven: 'Maven 3.5.0', globalMavenSettingsConfig: "GlobalMavenSettings.xml.20171122") { 
				 			if(isUnix()) {
				 				sh "./mvnw clean install " 
							} else { 
				 				bat "mvn clean install " 
							} 
				 } 
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
