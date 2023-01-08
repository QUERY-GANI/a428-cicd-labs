node {
    env.NODEJS_HOME = "${tool 'nodejs 18.13.0'}"
    env.PATH="${env.NODEJS_HOME}/bin:${env.PATH}"
    stage('Build') {
        sh 'npm install'
    }
    stage('Test') {
        sh './jenkins/scripts/test.sh'
    }
}