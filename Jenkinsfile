pipeline {
    agent any
    
    stages {

        stage("build") {

            when {
                expression {
                    BRANCH_NAME == 'main'
                }
            }

            steps {
                echo "building the application"

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
