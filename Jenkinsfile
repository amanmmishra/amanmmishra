pipeline {
    agent any
    parameters {
      choice(name: 'VERSION', choices: ['1.1.0','1.2.0','1.3.0'])
      booleanParam(name: 'status', defaultValue: true, description: 'boolean expression')
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
        echo 'Build successfully executed...'
      }
      failure{
        echo 'Build failed. Please check the logs for further information....'
      }
      
    }
    }   
