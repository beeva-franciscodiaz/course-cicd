node('master') {
  stage('Checkout') {
    deleteDir()
    git credentialsId: 'efa6f872-970c-4689-8554-9156caaa0fb8', url: 'git@github.com:beeva-franciscodiaz/course-cicd.git'
  }

  stage('Test') {
    sh './simplehttpserver/tests/unittests.sh ./simplehttpserver/'
  }

  stage('Package and publish') {
    sh "tar -zcvf simplehttpserver-${env.JOB_NAME}-${env.BUILD_ID}.tar.gz ./simplehttpserver"
    sh "aws s3 cp simplehttpserver-${env.JOB_NAME}-${env.BUILD_ID}.tar.gz s3://clase-gendevops2-cicd-ci/"
  }
}
