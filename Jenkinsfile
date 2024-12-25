pipeline{
    agent any
    tools{
        jdk 'Java17'
        maven 'Maven3'
    }
    stages{
        stage("Clean up workspace"){
            steps{
               echo '============== Clean up workspace =============='
               cleanWs()
            }

        }
         stage("Check up workspace"){
            steps{
               echo '============== Check up workspace =============='

               git branch: 'main', credentialsId: 'github', url: 'https://github.com/Khmoussi/jenkins-demo-app.git'
            }

        }
           stage("Build application "){
            steps{
               echo '============== Build application =============='
               sh "mvn clean package"
            }

        }
           stage("Test application "){
            steps{
               echo '============== Test application =============='                
               sh "mvn test"
            }

        }
    }
}