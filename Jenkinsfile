pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    // Retrieve SSH credentials dynamically
                    def sshCredentials = credentials('SSH_SERVER')
                    
                    if (sshCredentials != null) {
                        // Start an SSH agent with the dynamically retrieved credentials
                        sshagent(credentials: [${sshCredentials}]) {
                            // Execute your shell script on the remote host
                            sh 'ssh Administrator@100.25.17.128 "/c/Users/Administrator/Desktop/test.sh"'
                        }
                    } else {
                        error('Failed to retrieve SSH credentials')
                    }
                }
            }
        }
    }
}
