node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("ahyoon97/flask-example")
         
     }
     stage('Push image') {
         docker.withRegistry('https://registry.hub.docker.com', 'harbor_cred') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}
