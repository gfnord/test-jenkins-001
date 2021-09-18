pipeline {
    agent any
    stages {
        stage('Staging') {
            steps {
                retry(3) {
                    sh '''
                        echo "Ping loraserver..."
                        ping -c 3 10.150.1.198
                    '''
                }
                timeout(time: 1, unit: 'MINUTES') {
                    sh 'echo "Timeout reached"'
                }
            }
        }
    }
}
