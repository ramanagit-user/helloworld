// A simple multibranch scripted pipeline
// Replace the entries <an actual .*>
// with values from your jenkins instance

node('<an actual build agent label>') {
    // check out the repository listed when setting up the multibranch pipeline
    stage('checkout') {
        checkout scm
    }

    // the build stage will use the wrapper to run the default gradle task
    // assumes that you can pass artifactoryUser and artifactoryPass
    // to the gradle script for artifactory access,  normally these are
    // in the users gradle.properties, but that is not really an option
    // on CI servers
    stage('build') {
        withCredentials([usernamePassword(credentialsId: '<an actual credentialsId in jenkins>', usernameVariable: 'username', passwordVariable: 'password')]) {
            sh "sh ./gradlew -PartifactoryUser=$username -PartifactoryPassword=\'$password\' --refresh-dependencies"
        }
    }
}
