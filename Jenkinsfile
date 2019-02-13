pipeline {
    agent any
    stages {
        stage('Clone Front A-B') {
            steps {
                sh "git clone https://github.com/ScastellanosM/movie-analyst-ui.git"
                sh "rm -rf movie-analyst-ui"
            }
        }
        stage('Build Front A-B'){
            steps {
                sh "zip -r movie-analyst-ui.zip /var/lib/jenkins/workspace/FrontA_master"      
            }
        }
        stage('Deploy Front Server A'){
            steps {
               sh "scp -i /home/ubuntu/SantiagoCastellanos.pem -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/FrontA_master/movie-analyst-ui.zip ubuntu@11.0.1.17:/home/ubuntu"
           }
        }  
        stage('Deploy Front Server B'){
            steps {
               //sh "scp -i /home/ubuntu/SantiagoCastellanos.pem -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/FrontA_master/movie-analyst-ui.zip ubuntu@11.0.2.108:/home/ubuntu"
               sshPublisher(publishers: [sshPublisherDesc(configName: 'ubuntu@11.0.1.17', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'echo "Hello"', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/home/ubuntu', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'movie-analyst-ui.zip')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
           }
        } 
       /* stage('Deploy Back Server '){
            steps {
               sh "scp -i /home/ubuntu/SantiagoCastellanos.pem /var/lib/jenkins/workspace/FrontA_master/movie-analyst-ui.zip ubuntu@11.0.1.17:/home/ubuntu"
           }
        }*/     
    }
}
  