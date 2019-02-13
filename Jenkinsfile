pipeline {
    agent any
    stages {
        stage('Build Front'){
            steps { 
                dir('/var/lib/jenkins/workspace') {
                    sh "tar -zcvf movieanalyst-website.tar.gz FrontA_master"
                    sh "mkdir -p Artifacts_repo" 
                    sh "mv movieanalyst-website.tar.gz Artifacts_repo"
            }     
            }
        }
        stage('Deploy Front Server A'){
            steps {
                dir('/var/lib/jenkins/workspace/Artifacts_repo') {               
                sshPublisher(publishers: [sshPublisherDesc(configName: 'ubuntu@11.0.1.17', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'tar xvzf movieanalyst-website.tar.gz &&  rsync -rpa FrontA_master/ movieanalyst-website && pm2 stop && pm2 start', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'tar xvzf movieanalyst-website.tar.gz')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])        
           }
           }
        }  
        stage('Deploy Front Server B'){
            steps {
               dir('/var/lib/jenkins/workspace/Artifacts_repo') { 
               sshPublisher(publishers: [sshPublisherDesc(configName: 'ubuntu@11.0.2.108', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'tar xvzf movieanalyst-website.tar.gz  &&  rsync -rpa FrontA_master/ movieanalyst-website && pm2 stop && pm2 start', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'tar xvzf movieanalyst-website.tar.gz')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
           }     
           }       
        } 
    }
}

  