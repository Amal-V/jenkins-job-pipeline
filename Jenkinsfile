node {
    stage('Build') {
        echo 'Building....'
        sh 'git clone https://github.com/Amal-V/jenkins-job-pipeline.git'
        sh 'docker build -t node-docker .'
    }
    stage('Test') {
        echo 'Testing....'
        sh 'docker images'
        sh 'docker ps -a'
    }
    stage('Deploy') {
        echo 'Deploying....'
    }
}