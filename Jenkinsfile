def alias
pipeline {
    environment {
        ALIASA = true
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
                ALIASA = ${env.ALIASA}
                """
                script {
                    alias = load 'alias.groovy'
                    print(alias.randum())
                }
            }
        }
    }
    post {
        aborted {
            echo 'ajaj'
        }
    }
}
