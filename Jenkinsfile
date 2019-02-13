pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                sh "git clone https://github.com/ScastellanosM/movie-analyst-ui.git"
                sh "rm -rf movie-analyst-ui"
            }
        }
        stage('Build'){
            steps {
                sh "zip -r movie-analyst-ui.zip /var/lib/jenkins/workspace/FrontA_master"      
            }
        }
        stage('Deploy'){
            steps {
               sh "scp -i /home/ubuntu/SantiagoCastellanos.pem /var/lib/jenkins/workspace/FrontA_master/movie-analyst-ui.zip ubuntu@11.0.1.17:/home/ubuntu"
               //  sshPublisher(publishers: [sshPublisherDesc(configName: 'ubuntu@11.0.1.17', transfers: [sshTransfer(cleanRemote: true, excludes: '', execCommand: 'scp -i /home/ubuntu/\\"SantiagoCastellanos.pem\\" /var/lib/jenkins/workspace/FrontA_master/movie-analyst-ui.zip ubuntu@11.0.1.17:/home/ubuntu', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/home/ubuntu', remoteDirectorySDF: false, removePrefix: 'FrontA_master', sourceFiles: 'FrontA_master/*.zip', useAgentForwarding: true)], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
           }
        }    
    }
}
  