pipeline {
    agent {
        node {
            label "maven"
        }
    }

    stages {
        stage('Git Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/shrikantnmath/tweet-trend-new.git'
            }
        }
    }
}
