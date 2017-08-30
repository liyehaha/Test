pipeline {
  agent any
  stages {
    stage('Test') {
      steps {
        parallel(
          "Test": {
            git(url: 'git@github.com:YunzhanghuOpen/geass.git', branch: 'issue#1071', changelog: true)
            
          },
          "Build": {
            sh 'printenv'
            
          },
          "Unitest": {
            sh 'echo \'unitest\''
            
          }
        )
      }
    }
    stage('Docker') {
      steps {
        build(quietPeriod: 1, job: 'geass')
      }
    }
    stage('Qa') {
      steps {
        sh 'echo \'qa\''
      }
    }
    stage('Deploy') {
      steps {
        build 'aliyun-slb-automate'
      }
    }
  }
}