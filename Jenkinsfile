pipeline {
        agent any
        tools {
                'NodeJS'
        }

        stages {
                stage('Checkout Github'){
                        steps {
                                git branch: 'main', credentialsId: 'jenkins-git-docker', url: 'https://github.com/slinetworks/NodeJsApp.git'

                        }
                }
                stage('Install node dependencies'){
                        steps {
                                sh 'npm install'
                        }
               }
                stage('Test Code'){
                        steps {
                                sh 'npm test'
                        }
                  }
          }

          post {
                  success {
                          echo 'Build completed succesfully!'
                  }
                  failure {
                          echo 'Build failed. Check logs.'
                    }
            }
  }
