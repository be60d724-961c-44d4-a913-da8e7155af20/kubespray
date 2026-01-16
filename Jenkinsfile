pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh '''#!/usr/bin/env bash

echo "Demo"'''
          }
        }

        stage('Build OSX') {
          steps {
            sleep 45
          }
        }

      }
    }

    stage('Aritifacts') {
      steps {
        fingerprint(defaultExcludes: true, targets: 'bin/server')
        archiveArtifacts 'bin/server'
      }
    }

  }
  environment {
    ENV = ''
    BRANCH = ''
  }
}