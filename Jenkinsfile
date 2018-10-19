pipeline {
  agent any
  tools {
    gradle 'Default'
  }
  stages {
    stage("Build") {
      steps {
        sh "python -m py_compile main.py"
      }
    }
    stage("Test") {
      steps {
        sh "python -m doctest main.py"
      }
    }
  }
}
