node {
  stage('Build') {
    sh 'pwd'
    dir("../${env.WORKSPACE}@script") {
      sh 'printenv'
      sh 'pwd'
      sh "${env.WORKSPACE}@script/sbt update"
      sh "${env.WORKSPACE}@script/sbt all"
      // sh "${tool name: 'sbt-0.13.13', type: 'org.jvnet.hudson.plugins.SbtPluginBuilder$SbtInstallation'}/bin/sbt update"
      // sh "${tool name: 'sbt-0.13.13', type: 'org.jvnet.hudson.plugins.SbtPluginBuilder$SbtInstallation'}/bin/sbt all"
    }
  }
  stage('Test') {
    sh "${tool name: 'sbt-0.13.13', type: 'org.jvnet.hudson.plugins.SbtPluginBuilder$SbtInstallation'}/bin/sbt netlogo/depend"
    sh "${tool name: 'sbt-0.13.13', type: 'org.jvnet.hudson.plugins.SbtPluginBuilder$SbtInstallation'}/bin/sbt netlogo/test:fast"
    // sh "${env.WORKSPACE}@script/sbt headless/depend"
    // sh "${env.WORKSPACE}@script/sbt netlogo/test:fast"
    // sh "${env.WORKSPACE}@script/sbt parserJS/test"
    // sh "${env.WORKSPACE}@script/sbt nogen netlogo/test:fast"
    // sh "${env.WORKSPACE}@script/sbt threed netlogo/test:fast"
    // sh "${env.WORKSPACE}@script/sbt headless/test:fast"
    // sh "${env.WORKSPACE}@script/sbt netlogo/test:medium"
    // sh "${env.WORKSPACE}@script/sbt nogen netlogo/test:medium"
    // sh "${env.WORKSPACE}@script/sbt headless/test:medium"
    // sh "${env.WORKSPACE}@script/sbt nogen headless/test:medium"
    // sh "${env.WORKSPACE}@script/sbt netlogo/test:slow"
    // sh "${env.WORKSPACE}@script/sbt threed netlogo/test:slow"
    // sh "${env.WORKSPACE}@script/sbt netlogo/test:extensionTests"
    junit 'netlogo-gui/target/test-reports/*.xml'
  }
}
