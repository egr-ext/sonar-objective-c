node('macosx-4') {
    checkout scm

    def mvnHome = tool name: 'mvn'

    /* Set JAVA_HOME, and special PATH variables. */
    List javaEnv = [
        "M2_HOME=${mvnHome}",
    ]

    withEnv(javaEnv) {
        stage ('Initialize') {
            sh '''
                echo "PATH = ${PATH}"
                echo "M2_HOME = ${M2_HOME}"
            '''
        }
        stage ('Build') {
            try {
                sh 'mvn clean package'
            } catch (e) {
                currentBuild.result = 'FAILURE'
            }
        }
    }
}