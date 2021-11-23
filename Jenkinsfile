pipeline {
    agent{ label 'master'}

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
    }

    stages {
        stage('Checkout') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'main' , url: 'https://github.com/sandeepdingria/SpringPetClinic.git'
            }
        }
        stage('build'){
                // Run Maven on a Unix agent.
                steps{
                    sh 'mvn compile'
                }
        }
         stage('Test'){
                // Run Maven on a Unix agent.
                steps{
                    sh 'mvn test'
                }
        }
        
          stage('Package'){
                // Run Maven on a Unix agent.
                steps{
                    sh 'mvn package'
                }
        }


 stage('deploy'){
                // Run Maven on a Unix agent.
                steps{
                    sh 'java -jar /var/lib/jenkins/workspace/PetClinicPipeline/target/*.jar'
                }
        }

          
    }

}
