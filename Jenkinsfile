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

    stage('\'Increment-pom file\'') {
      steps {
        sh '''cd spring-boot-package-war
mvn build-helper:parse-version versions:set -DnewVersion=0.0.2.$BUILD_ID-SNAPSHOT versions:commit
'''
      }
    }

    stage('slack notification') {
      steps {
        slackSend(channel: 'int-project', message: 'o.k', notifyCommitters: true, token: '6yvX4UpUPCVnQBHQHySVMSR6')
      }
    }

  }
}