pipeline {
  agent any
  stages {
    stage('env') {
      steps {
        echo 'hello pipeline'
        ws(dir: 'C:/') {
          echo 'DIR'
        }
        
      }
    }
    stage('build') {
      steps {
        bat(script: 'sh mvn clean', returnStatus: true)
      }
    }
    stage('test') {
      steps {
        timeout(unit: 'MINUTES', time: 5)
      }
    }
    stage('prod') {
      steps {
        sleep 5
      }
    }
    stage('') {
      steps {
        archiveArtifacts(caseSensitive: true, fingerprint: true, artifacts: 'artifact')
      }
    }
  }
}