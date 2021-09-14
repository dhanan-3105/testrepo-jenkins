
pipeline {
agent any
stages {
stage('Build1'){
    steps{
        
            script{
                git 'https://github.com/dhanan77/testrepo-jenkins.git'
                app = docker.build("dnarasim248/simplebuildwithjenkins")
                docker.withRegistry( "https://registry.hub.docker.com", "dockerhub" ) {
                // dockerImage.push()
                app.push("latest")
            }
        
    }
}


stage('Orchestrate')
{
    steps{
        script{
    sh 'kubectl version --client'
        }
    }
}

}
}
