node('master') {
  stage('Checkout') {
    deleteDir()
    git credentialsId: '10b2c3b8-4a2c-476f-ac57-cb3266e1680a', url: 'git@github.com:beeva/corse-cicd.git'
  }
}
