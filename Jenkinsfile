node{

  git branch: "master", url: "http://192.168.100.185:3000/parsa/Django_cicd" 

  stage ('Build the Docker image') {
    sh "echo building the image..."
    sh "docker build --tag django_test:latest ."
    sh "echo building image complete."

  }

  stage ('Deploy the Docker image') {
    sh "echo Deploying the container..."
    sh " docker rm -f django_test"
    sh "docker run -d -p 192.168.100.146:8000:8000 --name django_test  django_test:latest "
    sh "echo Container successfully deployed."

  }

}