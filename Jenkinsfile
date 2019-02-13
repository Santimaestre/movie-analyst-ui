pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                customWorkspace '/home/ubuntu'
                sh "git clone https://github.com/ScastellanosM/movie-analyst-ui.git"
                sh "rm -rf movie-analyst-ui"
            }
        }
    }
}
  
