pipeline {
  agent { label "master" }
  environment {
    registry = "aqayumacrcontainer.azurecr.io/sample-angular-app-image"
    registryCredential = 'azure-cred'
  }
  stages {
    
   stage('Create Docker Image') {
     steps {       
       sh 'docker build -t qayumacrcontainer/sample-angular-app-image:latest  .'
     }
  }      
        stage ('Push image to Artifactory') { // take that image and push to acr registry
        steps {
          sh 'docker push "qayumacrcontainer.azurecr.io/sample-angular-app-image:1.0"'
        }
    }
        
    
  }
}
