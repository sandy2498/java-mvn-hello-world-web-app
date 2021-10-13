pipeline {
  agent {label 'slave_s1'}
  stages {
   
stage ('build'){
      steps{
        sh 'pwd'
        sh 'ls'
        sh 'docker build -t mavenimage:latest .'
      }
    }
   
     stage ('publish'){
      steps{
        sh 'docker tag mavenimage:latest sandy2498/mavenimage1:1.0'
        sh 'docker login -u sandy2498 -p Ajja@2498'
        sh 'docker push sandy2498/mavenimage1:1.0'
      }
    }
   
  stage ('deploy'){
    agent {label 'slave4'}
      steps{
        sh 'docker login -u sandy2498 -p Ajja@2498'
        sh 'docker pull sandy2498/mavenimage1:1.0'
        sh 'docker run -d -p 9000:8080 sandy2498/mavenimage1:1.0'
      }
    }
   
  stage ('deploy'){
    agent {label 'slave4'}
      steps{
        sh 'docker login -u sandy2498 -p Ajja@2498'
        sh 'docker pull sandy2498/mavenimage1:1.0'
        sh 'docker run -d -p 9000:8080 sandy2498/mavenimage1:1.0

  }
}
