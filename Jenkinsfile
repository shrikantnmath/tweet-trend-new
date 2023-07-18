pipeline {
    agent {
        node {
            label "maven"
        }
    }
environment {
    PATH = "/opt/apache-maven-3.9.3/bin:$PATH"
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
        stage("build"){
            steps {
                 echo "----------- build started ----------"
                sh 'mvn clean deploy -Dmaven.test.skip=true'
                 echo "----------- build complted ----------"
            }
        }
        stage('SonarQube analysis') {
    environment {
      scannerHome = tool 'sonar-scanner'
    }
    steps{
    withSonarQubeEnv('sonarqube-server') { // If you have configured more than one global server connection, you can specify its name
      sh "${scannerHome}/bin/sonar-scanner"
    }
       }
      }
    }
}
