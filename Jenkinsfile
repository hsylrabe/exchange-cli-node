pipeline {
    agent any
    stages {
        stage('Install Dependencies') {
            agent {
                docker { image 'node:latest' }   
            }
            steps {
                sh 'npm ci'
              } 
       }
        stage('Unit Test') {
            agent {
                docker { image 'node:16.13.1-alpine' }   
            }
            steps {
                sh 'npm test'
            }
      } 
        stage ('Build') {
            agent {
                docker { image 'node:16.13.1-alpine' }   
            }
            steps {
            sh "npm run build"
            }
        }
        stage ('Unit Tests') {
            agent {
                docker { image 'node:16.13.1-alpine' }   
            }
            steps {
             sh "npm run test:unit"   
            }
        }
        stage ('Functional Test') {
            agent {
                docker { image 'node:16.13.1-alpine' }   
            }
            steps {
             sh "npm run test:functional"   
            }
        }
    } // stages
} // pipeline
