node {
    git branch: 'master', url: 'https://github.com/Amal-V/jenkins-job-pipeline.git'
    stage('Build') {
        echo 'Building....'
        sh 'docker build -t mynginx .'
    }
    stage('Test') {
        echo 'Testing....'
        sh 'sudo docker images'
        sh 'sudo docker ps -a'
    }
    stage('Deploy') {
        // sh 'sudo docker run -d node-docker'
        echo 'Deploying....'
    }
}