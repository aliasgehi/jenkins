pipeline {
    environment {
        ALIAS = true
    }
    agent any
    stages {
        stage('test') {
            input {
                message 'continue?'
                ok 'yEs'
            }
            steps {
                echo """
                ${env.JOB_NAME}
                ${env.BUILD_ID}
                ${env.NODE_NAME}
                ${env.WORKSPACE}
                ALIAS = ${env.ALIAS}
                """
            }
            
        }
    }
    post {
        aborted {
            echo 'ajaj'
        }
    }
}
