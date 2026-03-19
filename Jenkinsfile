pipeline {
   agent any

   stages {

       stage('Build Docker Image') {
           steps {
               bat '"C:\\Program Files\\Docker\\Docker\\resources\\bin\\docker.exe" build -t flask-cicd-app:latest .'
           }
       }

      stage('Load Image to Minikube') {
    steps {
        bat '"C:\\Program Files\\Kubernetes\\Minikube\\minikube.exe" image load flask-cicd-app:latest'
    }
}

       stage('Deploy to Kubernetes') {
           steps {
               bat '"C:\\Program Files\\Kubernetes\\kubectl.exe" apply -f deployment.yaml'
               bat '"C:\\Program Files\\Kubernetes\\kubectl.exe" apply -f service.yaml'
           }
       }
   }
}
