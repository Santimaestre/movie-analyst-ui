pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh "rm -rf movie-analyst-ui"
                sh "git clone https://github.com/ScastellanosM/movie-analyst-ui.git"
                sh "rm -rf movie-analyst-ui"
            }
        }
    }
}
  
