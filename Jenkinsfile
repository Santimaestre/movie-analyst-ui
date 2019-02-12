pipeline {
    agent any
    stages {
        stage('clone repo and cleant it') {
            steps {
                sh "rm -rf movie-analyst-ui"
                sh "git clone https://github.com/ScastellanosM/movie-analyst-ui.git"
                sh "mvn clean -f movie-analyst-ui"
            }
        }
    }
}
  
