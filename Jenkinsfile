#! 6d8d3232-848a-4f2e-8cbd-f889a2026c1f
pipeline {
    agent any
    environment {
        NEW_VERSION = '1.3.0'
        SERVER_CREDENTIALS = credentials('6d8d3232-848a-4f2e-8cbd-f889a2026c1f')
    }
    tools {
        maven 'Maven'
    }
    stages {

        stage("build") {

            when {
                expression {
                    BRANCH_NAME == 'main'
                    sh "mvn install"
                }
            }

            steps {
                echo "building the application"
                echo "building version ${NEW_VERSION}"

            }
        }
                stage("test") {

            when {
                expression {
                    BRANCH_NAME == 'dev'
                }
            }
            steps {
                echo "Testing App"
                
            }
        }
        stage("deploy") {

            steps {
                echo "Deploy app"
                
            }
        }
    }
}
