pipeline{
    agent any
    stages {
        stage("NPM Install"){
            steps{
                bat 'npm install'
            }
         }
        stage("NPM Audit"){
            steps{
                bat 'npm audit'
            }
         }
        stage("Run integration tests"){
            steps{
                bat 'npm test'
            }
         }
        stage('Deploy') {
            steps {
                script {
                    input message: 'Approve deployment?', ok: 'Deploy To Production'
                    echo 'Deploying'
                }
            }
        }
    }
}