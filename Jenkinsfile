pipeline {
    agent {
        docker { image 'node:16.13.1-alpine'}   
    }
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
        stage ('Unit Tests') {
            steps {
             sh "npm run test:unit"   
            }
        }
        stage ('Functional Test') {
            steps {
             sh "npm run test:functional"   
            }
        }
    } // stages
} // pipeline
