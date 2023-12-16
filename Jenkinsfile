pipeline {
    agent any
    environment{
      EMAIL_ADDRESS = "aman.mishra@simpplr.com"
      CURRENT_DATE = sh (script: 'date +"%Y-%M-%d"', returnStdout: true).trim()
    }
    parameters {
      choice(name: 'VERSION', choices: ['1.1.0','1.2.0','1.3.0'])
      booleanParam(name: 'status', defaultVlue: true, description: 'boolean expression')
    }
    stages {
        stage("build") {
            steps {
              echo 'building the application...'
            }
        }
        stage("test") {
          when {
            expression {
              params.status
            }
          }
            steps {
              echo 'testing the application...'
            }
        }
        stage("deploy") {
            steps {
              echo 'deploying the application...'
              echo "Version: ${VERSION}"
              echo "status: ${status}"
            }
        }
    }
        post {
          success{
            script {
              emailext attachLog: false,
              to:"${EMAIL_ADDRESS}"
              subject: "build excuted successfully at ${CURRENT_DATE}"
              body: """<html>
                           <body>
                               <p>"build excuted successfully at ${CURRENT_DATE}"</p>
                               </body>
                               </html>"""
            }
            }
          }
    }   
