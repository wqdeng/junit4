pipeline {
  agent any
  stages {
    stage('Start') {
      steps {
        sh 'echo \'Start\''
      }
    }
    stage('Git Clone...') {
      steps {
        echo 'Git Clone...'
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfiguration: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/junit-team/junit4.git']]])
      }
    }
  }
  environment {
    JAVA_HOME = '/Library/Java/JavaVirtualMachines/jdk1.8.0_221.jdk/Contents/Home'
  }
}
