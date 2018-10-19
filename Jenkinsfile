pipeline {
  agent any
  tools {
    gradle 'Default'
  }
  stages {
    stage("Build") {
      steps {
        sh "gcc main.c"
      }
    }
    stage("Test") {
      steps {
        sh "./a | grep -q 'hello world'"
      }
    }
  }
}
