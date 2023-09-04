pipeline {
    agent {
        label "worker-1"
    }
    tools {
        jdk 'java17'
        maven 'MVN-3.9.4'
    }
    stages {
        stage ("Cleanup Workspace"){
            steps {
                cleanWs()
            }
        }
  
        stage ("Checkout from SCM"){
            steps {
                git branch: 'main', 'github', url: 'https://github.com/asadanas/complete-prodcution-e2e-pipeline.git'
            }
        }

        stage ("Build Application"){
            sh "mvn clean package"
        }
        
        stage ("Test Application"){
            sh "mvn test"
        }
    }
}