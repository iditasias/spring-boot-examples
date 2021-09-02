pipeline {
  agent any
  stages {
    stage('CheckoutCode') {
      steps {
        git(url: 'https://github.com/iditasias/spring-boot-examples.git', branch: 'iditortdanny_2_sol', changelog: true)
      }
    }

    stage('Mvn compile') {
      steps {
        sh '''cd sprint-boot-package-war
mvn compile'''
      }
    }

    stage('test') {
      steps {
        sh '''cd spring-boot-package-war
mvn test'''
      }
    }

  }
}