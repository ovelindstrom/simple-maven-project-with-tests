node {
    // Mark the code checkout 'stage'....
    stage 'Checkout'

    // Get some code from a GitHub repository
    git url: 'https://github.com/ovelindstrom/simple-maven-project-with-tests.git'

    // Get the maven tool.
    // ** NOTE: This 'M3' maven tool must be configured
    // **       in the global configuration.
    def mvnHome = tool 'M3_99'
    env.PATH = "${mvnHome}/bin:${env.PATH}"

    // Mark the code build 'stage'....
    stage 'Assemble'
    // Run the maven build
    sh 'mvn clean install'

    // Mark the code verify 'stage'....
    stage 'Test'
    sh 'mvn -B verify'

    // Mark the code report stage
    stage 'Fuck it up'
    input id: 'DeployIt', message: 'Deploy it', ok: 'Hell Yah!'

}
