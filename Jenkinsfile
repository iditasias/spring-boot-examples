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
        sh '''cd spring-boot-package-war
mvn compile'''
      }
    }

    stage('Test {mvn test}') {
      steps {
        sh '''cd spring-boot-package-war
mvn test'''
      }
    }

    stage('Package{mvn clean package}') {
      steps {
        sh '''cd spring-boot-package-war
mvn clean package'''
      }
    }

  }
}