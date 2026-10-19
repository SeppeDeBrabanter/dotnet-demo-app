node {
    stage('Checkout') {
        checkout scm
    }
    stage('Deploy') {
        sh 'docker compose -p todoapp up -d --build'
    }
    stage('Test') {
        sh 'curl -fsS --retry 10 --retry-delay 3 --retry-all-errors http://172.16.0.10:8081/ > /dev/null'
    }
}