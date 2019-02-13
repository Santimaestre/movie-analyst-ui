pipeline {
    agent any
    stages {
        stage('clone repo and cleant it') {
            steps {
                sh "cd "
                sh "rm -rf movie-analyst-ui"
                sh "git clone https://github.com/ScastellanosM/movie-analyst-ui.git"
            }
        }
    }
}
  
