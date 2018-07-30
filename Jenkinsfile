node('macosx-4') {
    checkout scm

    stage ('Build') {
        try {
            sh 'mvn clean package'
        } catch (e) {
            currentBuild.result = 'FAILURE'
        }
    }
}