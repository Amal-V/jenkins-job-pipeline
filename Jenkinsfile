node {
    stage('Checkout') {
        echo 'Branch checkout....'
        git branch: 'master', url: 'https://github.com/Amal-V/jenkins-job-pipeline.git'
    }
    stage('Build') {
        echo 'Building....'
        sh "docker build -t global-router ."
    }
    stage('Clone 2nd Repo ') {
        echo 'Branch Checkout....'
        git branch: 'amal/dev', credentialsId: 'amal-v', url: 'https://github.com/fastretailing/rewrite_unit_test.git'
    }
    
    stage('Test') {
        echo 'Testing....'
        sh 'sudo docker images'
        sh 'sudo docker ps -a'
    }
    stage('Deploy') {
        echo 'Deploying....'
        sh 'docker-compose up -d'
        echo 'Deploy Success....'
    }
}