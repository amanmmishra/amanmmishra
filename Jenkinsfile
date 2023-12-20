pipeline {
    agent any
    stages {
        stage ("building") {
            steps {
                echo 'building the app'
            }
        }
        stage ("testing") {
            when {
                expression {
                    BRANCH_NAME = 'qa'
                }
            }
            steps {
                echo 'testing the app'
            }

        }
        stage ("deploying") {
            steps {
                echo 'deploying the app'
            }

        }
    }
}
