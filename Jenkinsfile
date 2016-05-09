


node('linux') {
    // Get the maven tool.
    // ** NOTE: This 'M3' maven tool must be configured
    // **       in the global configuration.
    def mvnHome = tool 'M339'
    env.PATH = "${mvnHome}/bin:${env.PATH}"

    // Mark the code build 'stage'....
    stage 'Build'
    // Run the maven build
    sh 'mvn clean install'

    // Mark the code verify 'stage'....
    stage 'Verify'
    sh 'mvn -B verify'

    // Mark the code report stage
    stage 'Fuck it up'
    input id: 'DeployIt', message: 'Deploy it', ok: 'Hell Yah!'

}
