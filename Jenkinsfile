pipeline {
    agent any

    stages {
		stage ('checkout') {
	 	 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '182a98f6-79a5-4072-abac-ea4e9f48de7f', url: 'https://github.com/Zakharg/libra-jenkins-test-calculator.git']]]) 
		}
		stage ('maven build') {
 			// Maven build step
			withMaven(maven: 'Maven 3.5.0', globalMavenSettingsConfig: "GlobalMavenSettings.xml.20171122") { 
	 			if(isUnix()) {
	 				sh "./mvnw clean install " 
				} else { 
	 				bat "mvn clean install " 
				} 
 			} 
	}		
    }
}
