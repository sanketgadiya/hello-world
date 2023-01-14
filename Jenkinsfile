pipeline {
    agent none
	environment { 
        RELEASE_VERSION = 'RJ-2023.0-2023-01-12-eng2'
		PREVIOUS_RELEASE_VERSION = 'RI-2022.10'
		PRECREATED_WS_BRANCH = 'xjello_dev'
		isOSX = 'false'
    }
    stages {
        stage('XtTools Copy') {
			steps {
				node(label: 'vlno-tenfe02-rel') {
					dir("/usr/local/xrfs_s/xars/winXtDevTools/downloads"){
						sh 'mv $RELEASE_VERSION /usr/local/xrfs_s/xars/XtTools/'
					}
				}
			}
		}					
		stage('Windows Copy'){
			steps {
				node(label: 'vlno-tenfe02-rel') {
					dir("/usr/local/xrfs_s/xars/winXtDevTools/downloads"){
						sh 'mkdir -p $RELEASE_VERSION'
					}
					dir("/usr/local/xrfs_s/xars/winXtDevTools/downloads/$RELEASE_VERSION"){
						sh 'mkdir -p builds tools'
						sh 'cp /usr/local/xrfs_s/xars/XtTools/$RELEASE_VERSION/builds/*win32.tgz builds/'
						sh 'cp /usr/local/xrfs_s/xars/XtTools/$RELEASE_VERSION/tools/*win32.tgz tools/'
					}
					dir("/usr/local/xrfs_s/xars/winWS/$PRECREATED_WS_BRANCH"){
						sh 'cp -r $PREVIOUS_RELEASE_VERSION $RELEASE_VERSION'
					}
				}
			}
		}
		stage('Linux Copy'){
			steps{
				node(label: 'vlno-tenfe02-rel') {
					dir("/usr/local/xrfs_s/xars/linuxXtDevTools/downloads"){
						sh 'mkdir -p $RELEASE_VERSION'
					}
					dir("/usr/local/xrfs_s/xars/linuxXtDevTools/downloads/$RELEASE_VERSION"){
						sh 'mkdir -p builds tools'
						sh 'cp /usr/local/xrfs_s/xars/XtTools/$RELEASE_VERSION/builds/*linux.tgz builds/'
						sh 'cp /usr/local/xrfs_s/xars/XtTools/$RELEASE_VERSION/tools/*linux.tgz tools/'								
					}
					dir("/usr/local/xrfs_s/xars/linuxWS/$PRECREATED_WS_BRANCH"){
						sh 'cp -r $PREVIOUS_RELEASE_VERSION $RELEASE_VERSION'
					}
				}
			}
		}
		stage('macOSX Copy'){
			steps{
				node(label: 'vlno-tenfe02-rel') {
					script{
						if (env.isOSX == 'true') {
							dir("/usr/local/xrfs_s/xars/osxXtDevTools/downloads"){
								sh 'mkdir -p $RELEASE_VERSION'
							}
							dir("/usr/local/xrfs_s/xars/osxXtDevTools/downloads/$RELEASE_VERSION"){
								sh 'mkdir -p builds tools'
								sh 'cp /usr/local/xrfs_s/xars/XtTools/$RELEASE_VERSION/builds/*osx.tgz builds/'
								sh 'cp /usr/local/xrfs_s/xars/XtTools/$RELEASE_VERSION/tools/*osx.tgz tools/'										
							}
							dir("/usr/local/xrfs_s/xars/macosxWS/$PRECREATED_WS_BRANCH"){
								sh 'cp -r $PREVIOUS_RELEASE_VERSION $RELEASE_VERSION'
							}
						} else {
							echo 'macOSX tools and configs are not available'
						}
					}
				}	
			}
		}
		stage("vlpune-samba2 Copy"){
			steps{
				node(label: 'vlno-tenfe01') {
					dir("/usr/local/vlpune-samba2/downloads/"){
						sh 'cp -r /usr/local/xrfs_s/xars/XtTools/$RELEASE_VERSION .'
					}								
				}
			}
		}
		
		
		stage('Tool Installation') {
      parallel {
        stage('Windows') {
          steps {
            echo 'hi'
          }
        }

        stage('Linux') {
          steps {
            echo 'hi'
          }
        }

        stage('macOSX') {
          steps {
            echo 'hi'
          }
        }

      }
    }

    stage('Config Installation') {
      parallel {
        stage('Windows') {
          steps {
            echo 'hi'
          }
        }

        stage('Linux') {
          steps {
            echo 'hi'
          }
        }

        stage('macOSX') {
          steps {
            echo 'hi'
          }
        }

      }
    }

    stage('Source Path Setup') {
      parallel {
        stage('windows') {
          steps {
            echo 'hi'
          }
        }

        stage('Linux') {
          steps {
            echo 'hi'
          }
        }

        stage('macOSX') {
          steps {
            echo 'hi'
          }
        }

      }
    }

    stage('Simulator Setup') {
      parallel {
        stage('Windows') {
          steps {
            echo 'hi'
          }
        }

        stage('Linux') {
          steps {
            echo 'hi'
          }
        }

        stage('macOSX') {
          steps {
            echo 'hi'
          }
        }

      }
    }

    stage('Run Precreated WS ') {
      steps {
        echo 'hi'
      }
    }
		
    }
}
