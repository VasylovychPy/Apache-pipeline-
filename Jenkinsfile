pipeline {
    agent any

    stages {
        stage('Install Apache2 on Apache VM') {
            steps {
                sshagent(['my-ssh']) {
                    sh '''
ssh -o StrictHostKeyChecking=no vasylovych@192.168.1.108 << EOF
sudo apt update
sudo apt install -y apache2
sudo systemctl start apache2
sudo systemctl enable apache2
EOF
'''
                }
            }
        }
    }
}


