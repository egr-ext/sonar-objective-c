node('macosx-4') {
    checkout scm

    stage ('Build') {
        try {
            sh 'mvn'
        } catch (e) {
            currentBuild.result = 'FAILURE'
        }
    }
}