pipeline {
  agent any

  stages {

    stage('Checkout Application Git Branch') {
        steps {
            git credentialsId: 'repo-and-hook-access-token-credentials',
                url: 'https://github.com/kangseongwon1/test.git',
                branch: 'master'
        }
        post {
                failure {
                  echo 'Repository clone failure !'
                }
                success {
                  echo 'Repository clone success !'
                }
        }
     stage('Build Dockerfile') {
        steps {
             app = docker.build("github.com/kangseongwon1/test")
        }
        post {
                failure {
                  echo 'Docker Build test fail !'
                }
                success {
                  echo 'Docker Build test success !'
                }
        }     
    }
  }
  
}

