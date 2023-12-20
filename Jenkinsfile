pipeline {
    agent any
    environment {
        BUILD_VERSION = '11.2.0'
    }
    parameters {
        choice(name: 'COLOR', choices: ['Red','Blue','Green', 'Black'])
        booleanParam(name: 'YN', defaultValue: true, description: 'boolean expression')
    }
    stages {
        stage ("building") {
            steps {
                echo 'building the app'
                echo "BR_Name: ${BUILD_VERSION}, status: ${YN}"
            }
        }
        stage ("testing") {
            steps {
                echo 'testing the app'
                echo "BR_Name: ${BUILD_VERSION}, status: ${YN}"
            }

        }
        stage ("deploying") {
            steps {
                echo 'deploying the app'
                echo "BR_Name: ${BUILD_VERSION}, status: ${YN}"
            }

        }
    }
}
