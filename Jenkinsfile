pipeline {
  agent any

  stages {

    stage('Checkout Application Git Branch') {
        steps {
            git credentialsId: 'repo-and-hook-access-token-credentials',
                url: 'https://github.com/best-branch/my-app.git',
                branch: 'main'
        }
        post {
                failure {
                  echo 'Repository clone failure !'
                }
                success {
                  echo 'Repository clone success !'
                }
        }
    }
  }
  
}

