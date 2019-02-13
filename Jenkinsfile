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
                withCredentials([sshUserPrivateKey(credentialsId: 'ubuntu', keyFileVariable: /home/ubuntu/"SantiagoCastellanos.pem")]) {
                sh "scp -i  /var/lib/jenkins/workspace/FrontA_master/movie-analyst-ui.zip ubuntu@11.0.1.17:/home/ubuntu"
             }       
           }
        }     
    }
}
  
