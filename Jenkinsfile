pipeline {
  agent any

  stages {

    stage('Build') {
      steps {
        sh "${tool name: 'sbt', type: 'org.jvnet.hudson.plugins.SbtPluginBuilder$SbtInstallation'}/bin/sbt compile"
      }
    }

    stage('Test') {
      steps {
        sh "${tool name: 'sbt', type: 'org.jvnet.hudson.plugins.SbtPluginBuilder$SbtInstallation'}/bin/sbt test"
        junit '**/target/test-reports/*.xml'
      }
    }

  }

}
