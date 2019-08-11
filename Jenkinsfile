pipeline {
  agent any
  stages {
    stage('Building...') {
      steps {
        echo 'Building...'
        sh 'mvn clean compile package -Dmaven.test.skip=true'
      }
    }
    stage('Sonar Analysis...') {
      steps {
        echo 'Sonar Analysis...'
        sh 'sonar-scanner scan -X -Dsonar.host.url=http://127.0.0.1:9000 -Dsonar.projectName=JUnit -Dsonar.projectVersion=4.13 -Dsonar.sourceEncoding=UTF-8 -Dsonar.projectKey=JUnit -Dsonar.java.binaries=./target/classes -Dsonar.sources=./src/main/java -Dsonar.projectBaseDir=./'
      }
    }
  }
  environment {
    JAVA_HOME = '/Library/Java/JavaVirtualMachines/jdk1.8.0_221.jdk/Contents/Home'
  }
}