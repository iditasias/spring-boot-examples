pipeline {
  agent {
    node {
      label 'centos7-nodejs'
    }

  }
  stages {
    stage('CheckoutCode') {
      steps {
        git(url: 'https://github.com/iditasias/spring-boot-examples.git', branch: 'iditorydanny_2_sol', changelog: true)
      }
    }

    stage('mvn compile') {
      steps {
        sh '''cd /home/jenkins/jenkins/workspace/boot-examples_iditorydanny_2_sol@tmp/script.sh
mvn compile
'''
      }
    }

  }
}