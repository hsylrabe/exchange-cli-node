pipeline {
    agent any
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm ci'
              } 
       }
        stage('Unit Test') {
            steps {
                sh 'npm test'
            }
      } 
        stage ('Build') {
            steps {
            sh "npm run build"
            }
        }
    } // stages
} // pipeline
