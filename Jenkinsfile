node {
  stage('Build') {
    checkout scm
    sh "./sbt update"
    sh "./sbt all"
  }
  stage('Test') {
    checkout scm
    sh "./sbt depend"
    sh "./sbt headless/depend"
    sh "./sbt netlogo/test:fast"
    sh "./sbt parserJS/test"
    sh "./sbt nogen netlogo/test:fast"
    sh "./sbt threed netlogo/test:fast"
    sh "./sbt headless/test:fast"
    sh "./sbt netlogo/test:medium"
    sh "./sbt nogen netlogo/test:medium"
    sh "./sbt headless/test:medium"
    sh "./sbt nogen headless/test:medium"
    sh "./sbt netlogo/test:slow"
    sh "./sbt threed netlogo/test:slow"
    sh "./sbt netlogo/test:extensionTests"
    junit 'netlogo-gui/target/test-reports/*.xml'
  }
}
