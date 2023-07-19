pipeline {
    
    agent any

    tools {
       
        maven "MY_MAVEN"
    }

    
    stages {
        stage('clean and checkout') {
            steps {
            
             
                sh 'mvn clean'
                echo 'downloading github project...'
                git branch: 'main', credentialsId: 'crdentialsI', url: 'githubURL'
            }
            
     }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            
       
        stage('build') {
            steps {
                echo 'building...'
                sh 'mvn test-compile'
                echo 'finished building'
            }
        }

       

        stage('package') {
            steps {
                echo 'packaging...'
                sh 'mvn war:war'
                echo 'packaged'
            }
        }
    }

    
}
