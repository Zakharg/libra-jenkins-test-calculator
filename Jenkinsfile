pipeline {
    agent any 

    stages {
        stage ('Compile stage') {
            steps {
                withMaven(maven : 'Maven 3.5.0', globalMavenSettingsConfig: "GlobalMavenSettings.xml.20171122") {
                    sh 'mvn clean compile'
                }
            }
        }
        
        stage ('Testing Stage') {
            steps {    
                withMaven(maven : 'Maven 3.5.0', globalMavenSettingsConfig: "GlobalMavenSettings.xml.20171122") {
                    sh 'mvn test'
                }        
            }
        }
        
        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'Maven 3.5.0', globalMavenSettingsConfig: "GlobalMavenSettings.xml.20171122") {
                    sh 'mvn deploy'
                }
            }
        }
    }

}