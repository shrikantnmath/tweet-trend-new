pipeline {
    agent {
        node {
            label "maven"
        }
    }

    stages {
        stage('CLEAN WORKSPACE') {
            steps {
                cleanWs()
            }
        }
        stage('Git Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/shrikantnmath/tweet-trend-new.git'
            }
        }
    }
}
