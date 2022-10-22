pipeline {
    agent {
      label 'agent1'
    }
    options {
        buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr:'5', daysToKeepStr: '', numToKeepStr: '5')
        disableConcurrentBuilds()
    }

    stages {
        stage ('Hello') {
            steps {
                echo "hello"
            }
        }
        stage ('Cat README') {
            when {
                branch "fix-*"
            }
            steps {
                sh '''
                    cat README.md
                '''
            }
        }
    }

}