pipeline {
    
	agent any

   
    stages{
        
        stage('Git checkout'){
            steps {
             git 'https://github.com/rajdeepsingh642/argocd-cd.git'
            }
        }
       
        stage('updating k8s deployment'){
            steps{
                sh """
                cat deployment.yml
                sed -i 's/${JOB_NAME}.*/${JOB_NAME}:${BUILD_ID}/g' deployment.yml
                cat deployment.yml
                """
            }
        } 
    }
}
