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
                archiveArtifacts '/var/lib/jenkins/workspace/FrontA_master/*'         
            }
        }
    }
}
  
