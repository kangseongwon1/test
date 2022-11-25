node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("https://github.com/kangseongwon1/test")
         
     }
     stage('Push image') {
         docker.withRegistry('https://github.com/kangseongwon1', 'repo-and-hook-access-token-credentials') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}

stage('Build image') {
  app = docker.build("172.30.5.156/admin/flask-example")
}

stage('Push image') {
  docker.withRegistry('https://172.30.5.156', 'harbor-cred') 
  {
     app.push("${env.BUILD_NUMBER}")
     app.push("latest")
  }
}
