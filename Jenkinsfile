pipeline {
  agent none
  stages {
    stage('Initial Setup') {
      parallel {
        stage('XtTools Copy') {
          steps {
            node(label: 'vlno-tenfe02-rel') {
              sh '''echo \'mv $RELEASE_VERSION /usr/local/xrfs_s/xars/XtTools/\'
						'''
            }

          }
        }

        stage('win/linux/osx XtDevTools Copy') {
          steps {
            node(label: 'vlno-tenfe02-rel') {
              sh '''sh \'mkdir -p $RELEASE_VERSION\'
								sh \'cd $RELEASE_VERSION\'
								sh \'mkdir -p builds tools\'
								sh \'cp /usr/local/xrfs_s/xars/XtTools/$RELEASE_VERSION/builds/*win32.tgz builds/\'
								sh \'cp /usr/local/xrfs_s/xars/XtTools/$RELEASE_VERSION/tools/*win32.tgz tools/\'
								sh \'cd /usr/local/xrfs_s/xars/winWS/$PRECREATED_WS_BRANCH\'
								sh \'cp -r $PREVIOUS_RELEASE_VERSION $RELEASE_VERSION\''''
            }

          }
        }

      }
    }

  }
  environment {
    RELEASE_VERSION = 'RJ-2023.0-2023-01-12-eng2'
    PREVIOUS_RELEASE_VERSION = 'RI-2022.10'
    PRECREATED_WS_BRANCH = 'xjello_dev'
    isOSX = 'false'
  }
}