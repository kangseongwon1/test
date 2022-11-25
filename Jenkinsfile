node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("https://github.com/kangseongwon1/test")
         
     }
     stage('Push image') {
         docker.withRegistry('https://github.com/kangseongwon1', 'repo-and-hook-access-token-credentials') {

             app.push("latest")
         }
     }
}

stage('Build image') {
  app = docker.build("https://github.com/kangseongwon1/test")
}

stage('Push image') {
  docker.withRegistry('https://github.com/kangseongwon1', 'repo-and-hook-access-token-credentials') 
  {

     app.push("latest")
  }
}
