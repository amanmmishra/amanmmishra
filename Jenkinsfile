def gv
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
        stage ("begin"){
            steps {
                script {
                gv = load "s.groovy"
                }
            }
        }
        stage ("building") {
            steps {
                script {
                    gv.building()
                }
            }
        }
        stage ("testing") {
            steps {
                script {
                    gv.testing()
                }
            }

        }
        stage ("deploying") {
            steps {
                script {
                    gv.deploying()
                }
            }

        }
    }
}
