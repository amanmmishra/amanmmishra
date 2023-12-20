pipeline {
    agent any
    environment {
        BUILD_VERSION = '11.2.0'
    }
    stages {
        stage ("building") {
            steps {
                echo 'building the app'
                echo "BR_Name: ${BUILD_VERSION}"
            }
        }
        stage ("testing") {
            steps {
                echo 'testing the app'
                echo "BR_Name: ${BUILD_VERSION}"
            }

        }
        stage ("deploying") {
            steps {
                echo 'deploying the app'
                echo "BR_Name: ${BUILD_VERSION}"
            }

        }
    }
}
