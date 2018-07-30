node('macosx-4') {
    checkout scm

    stage ('Build') {
        def mvn_version = 'M3'
        withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ) {
            sh 'mvn clean package'
        }
    }
}