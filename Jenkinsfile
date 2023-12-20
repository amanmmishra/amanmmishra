pipeline {
    agent any
    environment {
        String (name: 'BR_Name', defaultValue: 'fun', description: 'string variable')
    }
    stages {
        stage ("building") {
            steps {
                echo 'building the app'
                echo "BR_Name: ${BR_Name}"
            }
        }
        stage ("testing") {
            steps {
                echo 'testing the app'
                echo "BR_Name: ${BR_Name}"
            }

        }
        stage ("deploying") {
            steps {
                echo 'deploying the app'
                echo "BR_Name: ${BR_Name}"
            }

        }
    }
}
