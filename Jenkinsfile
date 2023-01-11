node {
    env.NODEJS_HOME = "${tool '16.0.0'}"
    env.PATH = "${env.NODEJS_HOME}/bin:${env.PATH}"
    stage('Build') {
        sh 'npm install'
    }
    stage('Test') {
        sh './jenkins/scripts/test.sh'
    }
    stage('Manual Approval') {
        input(message: "Lanjutkan ke tahap Deploy?")
    }
    stage('Deploy') {
        sh './jenkins/scripts/deliver.sh'
        sleep 60
        sh './jenkins/scripts/kill.sh'
    }
}