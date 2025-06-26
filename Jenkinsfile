pipeline {
    agent any

    stages {
        stage('Check Apache Logs for Errors') {
            steps {
                sshagent(['my-ssh']) {
                    sh '''
ssh -o StrictHostKeyChecking=no vasylovych@192.168.1.108 << EOF
sudo grep 'HTTP/1.1" [45][0-9][0-9]' /var/log/apache2/access.log || echo "No 4xx or 5xx errors found"
EOF
                    '''
                }
            }
        }
    }
}

