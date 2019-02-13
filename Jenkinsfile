pipeline {
    agent any
    stages {
        stage('Build Front'){
            steps {
                sh " tar -zcvf movieanalyst-website.tar.gz FrontA_master"      
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
        // tar -xzvf movieanalyst-website.tar.gz
    }
}
  