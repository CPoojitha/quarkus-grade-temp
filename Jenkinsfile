pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
               
                'mvn -Dmaven.test.failure.ignore=true clean package'
               }
               }
               
               
       stage('Building image') {
            steps{
                
          'docker build -f src/main/docker/Dockerfile.jvm -t quarkus/hello-world-jvm .'
            }
            }
            stage('Deploying into k8s'){
            steps{
                   
                  'kubectl apply -f deployment.yaml'
                        }
            }
            
            
        }
        }
        
