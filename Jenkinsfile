pipeline {
    agent {
        label 'AGENT-1' 
    }
    options{
        timeout(time: 10, unit: 'MINUTES') 
        disableConcurrentBuilds() 
        retry(1) 
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo this is build'
            }
        }
        stage('Test') {
            steps {
                sh 'echo this is test'
            }
        }
        stage('Deploy') {
            steps { 
                sh 'echo this is deploy' 
                error 'pipeline failed' 
            }
        }
    }

    post{
        always{
            echo "this section runs always" 
            deleteDir() 
        }
        success{
            echo "this section runs when pipeline is success"
        }
        failure{
            echo "this section runs when pipeline is failure" 
        }
    }
} 