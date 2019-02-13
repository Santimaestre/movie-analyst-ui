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
              /* sh "scp -i /home/ubuntu/\"SantiagoCastellanos.pem\" /var/lib/jenkins/workspace/FrontA_master/movie-analyst-ui.zip ubuntu@11.0.1.17:/home/ubuntu"*/
                 sshPublisher continueOnError: true, failOnError: true, publishers: [sshPublisherDesc(configName: 'ubuntu@11.0.1.17', sshRetry: [retries: 2, retryDelay: 10000], transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/home/ubuntu', remoteDirectorySDF: false, removePrefix: '/var/lib/jenkins/workspace/FrontA_master', sourceFiles: '/var/lib/jenkins/workspace/FrontA_master/*.zip')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)]
           }
        }    
    }
}
  
