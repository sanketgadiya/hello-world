pipeline {
  agent any
  stages {
    stage('XtTools Copy') {
      steps {
        echo 'xtools'
      }
    }

    stage('Windows') {
      parallel {
        stage('Windows') {
          steps {
            echo 'win'
          }
        }

        stage('Linux') {
          steps {
            echo 'linux'
          }
        }

        stage('osx') {
          steps {
            echo 'osx'
          }
        }

        stage('vppin-samab2 ') {
          steps {
            echo 'asd'
          }
        }

      }
    }

    stage('end') {
      steps {
        echo 'end'
      }
    }

  }
}