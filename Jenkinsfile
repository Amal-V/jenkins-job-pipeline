node {
    def image_name="global-router"
    def test_file_loc='./test_server/test-urls.yml'

    stage('Checkout') {
        echo 'Branch checkout....'
        git branch: 'master', url: 'https://github.com/Amal-V/jenkins-job-pipeline.git'
    }
    stage('Build') {
        echo 'Building....'
        sh "docker build -t ${image_name} ."
    }
    stage('Clone 2nd Repo ') {
        echo 'Branch Checkout....'
        git branch: 'amal/dev', credentialsId: 'amal-v', url: 'https://github.com/fastretailing/rewrite_unit_test.git'
    }
    
    stage('Test') {
        echo 'Testing....'
        sh 'docker images'
    }
    stage('Deploy') {
        echo 'Deploying....'
        sh "export TESTCASES_FILE_PATH=${test_file_loc} && export NGINX_IMAGE=${image_name} && docker-compose up --build --force-recreate -d"
        sh 'curl http://localhost:6582/run-test > report.xml'
        sh "export TESTCASES_FILE_PATH=${test_file_loc} && export NGINX_IMAGE=${image_name} && docker-compose stop && docker-compose rm -f"
        echo 'Deploy Success....'
        junit 'report.xml'
    }
}
