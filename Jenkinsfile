node {
 stage('Clone repository') {
   git credentialsId: 'github_access_token', url: 'https://github.com/nals1212/web-count.git'
 }
 stage('Build image') {
   dockerImage = docker.build("bitdoc71/web_count:v1.0")
 }
 stage('Push image') {
   withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
   dockerImage.push()
   }
 }
}
