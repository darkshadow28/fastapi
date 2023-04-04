pipeline {
    
    agent any
    parameters {
        choice(name: 'VERSION', choices: ['1.1', '1.2'], description: 'version to deploy')
        booleanParam(name: 'executeTests', defaultValue: true, description: 'check if tests have to be run')
    }

    environment {
        NEW_VERSION = '1.3.0'
    }

    stages {

        stage("build") {

            steps {
                echo 'buildig the app...'
                echo "building version ${NEW_VERSION}"
            }
        }

        stage("test") {
            when {
                expression {
                    params.executeTests
                }
            }
            steps {
                echo 'testing the app...'
            }
        }

        stage("deploy") {

            steps {
                echo 'deploying the app...'
                echo "deploying version ${params.VERSION}"
            }
        }        
    }
}
