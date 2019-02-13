pipeline {
    agent any
    stages {
        stage('Clone Front A-B') {
            steps {
                sh "rm -rf movie-analyst-ui"
                sh "git clone https://github.com/ScastellanosM/movie-analyst-ui.git"
            }
        }
        stage('Build Front A-B'){
            steps {
                sh "zip -r movie-analyst-ui.zip /var/lib/jenkins/workspace/Front"      
            }
        }
        stage('Deploy Front Server A'){
            steps {
               sshPublisher(publishers: [sshPublisherDesc(configName: 'ubuntu@11.0.1.17', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'echo "Hello Front A"', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'movie-analyst-ui.zip')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
           }
        }  
        stage('Deploy Front Server B'){
            steps {
               sshPublisher(publishers: [sshPublisherDesc(configName: 'ubuntu@11.0.2.108', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'echo "Hello Front B"', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'movie-analyst-ui.zip')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
           }
        } 
    }
}
  