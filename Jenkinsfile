node {
    env.NODEJS_HOME = "${tool '18.13.0'}"
    env.PATH = "${env.NODEJS_HOME}/bin:${env.PATH}"
    env.NODE_TLS_REJECT_UNAUTHORIZED = 0
    stage('Build') {
        sh 'npm install'
    }
    stage('Test') {
        sh './jenkins/scripts/test.sh'
    }
    stage('Deploy') {
        sh './jenkins/scripts/deliver.sh'
        input message: 'Sudah selesai menggunakan React App? (Klik "Proceed" untuk mengakhiri)'
        sh './jenkins/scripts/kill.sh'
    }
}