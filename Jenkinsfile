pipeline{
    agent any

    environment{
        DOCKERHUB_USERNAME = "endgaurav"
        APP_NAME = "gitops-argo-app"
        IMAGE_TAG = "${BUILD_NUMBER}"
        IMAGE_NAME = "${DOCKERHUB_USERNAME}" + "/" + "${APP_NAME}"
        REGISTRY_CREDS = 'dockerhubcred'
    }
    stages{
        stage('Cleanup workspace'){
            steps {
                script {
                    cleanWs()
                }
            }
        }
        stage('Git checkout'){
            steps{
                script{

                    git credentialsId: 'github',
                     branch: 'main', 
                     url: 'https://github.com/EndGaurav/gitops-argocd-CI.git'
                }               
                
            }
        }
    }
}