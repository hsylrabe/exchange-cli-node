pipeline {
    agent {
        docker { image 'node:latest' }   
    }
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'sudo chown -R 973:973 "/.npm"'
                sh 'npm ci'
              } 
       }
        stage('Unit Test') {
            steps {
                sh 'sudo chown -R 973:973 "/.npm"'
                sh 'npm test'
            }
      } 
        stage ('Build') {
            steps {
                sh 'sudo chown -R 973:973 "/.npm"'
            sh "npm run build"
            }
        }
        stage ('Unit Tests') {
            steps {
                sh 'sudo chown -R 973:973 "/.npm"'
             sh "npm run test:unit"   
            }
        }
        stage ('Functional Test') {
            steps {
                sh 'sudo chown -R 973:973 "/.npm"'
             sh "npm run test:functional"   
            }
        }
    } // stages
} // pipeline
