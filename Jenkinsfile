pipeline {
     agent any

     environment {
         IMAGE_NAME = "app"
     }

     stages { 

         stage('Checkout Code') {
             steps {
                 git branch: 'main',
                     url: 'https://github.com/Jobsoumya/app'
             }
         }
       
         stage('Build Docker Image') {
             steps {
                 sh 'docker build -t $IMAGE_NAME .'
             }
         }

         stage('Run Docker Container') {
             steps {
                 sh '''
                   docker run --rm $IMAGE_NAME
                 '''
             }
         }
     }
}
