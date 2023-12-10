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
              env.BRANCH_NAME == 'test' && params.status
            }
          }
            steps {
              echo 'testing the application...'
              echo "BranchName: ${env.BRANCH_NAME}"
              echo "Status: ${params.status}"  
            }
        }
        stage("deploy") {
            steps {
              echo 'deploying the application...'
              echo "Version: ${params.VERSION}"
              echo "status: ${params.status}"
            }
        }
    }   
}
