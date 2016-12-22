node('master') {
  stage('Checkout') {
    deleteDir()
    git credentialsId: 'efa6f872-970c-4689-8554-9156caaa0fb8', url: 'git@github.com:beeva-franciscodiaz/course-cicd.git'
  }

  stage('Test') {
    sh './simplehttpserver/tests/nittests.sh ./simplehttpserver/'
  }
}
