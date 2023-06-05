pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven"
        jdk "java-11"
    }

    stages {
        
        stage('clone'){
          steps {
                // Get some code from a GitHub repository
                git 'https://github.com/dounmogni/CI-CD_Complet.git'
          }  
        }
        
        stage('Build') {
            steps {
                  // Run Maven on a Unix agent.
                sh "mvn clean install"
                
            }
        }
            
        stage('Copy Artifact') {
            steps { 
                  
		           sh '''
                      echo "Copy du .war vers /opt/projet"
                      pwd
		              cp -r webapp/target/*.war /opt/projet/
                 '''
		           
		           
            }
        }    
            

            
        
    }
}
