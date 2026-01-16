pipeline {
  agent none
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh '''#!/usr/bin/env bash

echo "Demo"'''
            mail(subject: 'test', body: 'test', bcc: 'yitong.bai@qq.com', cc: 'yitong.bai@qq.com', from: 'yitong.bai@qq.com', replyTo: 'yitong.bai@qq.com', to: 'yitong.bai@qq.com')
          }
        }

        stage('Build OSX') {
          steps {
            sleep 45
            bat 'fasdf'
          }
        }

        stage('Build MSI') {
          steps {
            build 'kubespray'
          }
        }

      }
    }

    stage('Upload') {
      steps {
        archiveArtifacts 'bin/app'
      }
    }

    stage('Finished') {
      steps {
        waitForBuild '${RunID}'
      }
    }

  }
  environment {
    ENV = ''
    BRANCH = ''
  }
}