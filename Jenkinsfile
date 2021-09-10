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

    stage('mvn comp') {
      steps {
        sh '''cd spring-boot-package-war
mvn compile'''
      }
    }

  }
}