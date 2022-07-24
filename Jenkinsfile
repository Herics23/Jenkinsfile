#! 6d8d3232-848a-4f2e-8cbd-f889a2026c1f
def gv
pipeline {
    agent any

    parameters {
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')

    }

    stages {

        stage("build") {

            when {
                expression {
                    BRANCH_NAME == 'main'
                }
            }

            steps {
                script {
                    gv.buildApp()
                }
                

            }
        }
                stage("test") {

            when {
                expression {
                    BRANCH_NAME == 'main'
                    params.executeTests == true

                }
            }
            steps {
                script {
                    gv.testApp()
                }

                
            }
        }
        stage("deploy") {

            steps {
                echo "Deploy app"
                echo "Deloying version ${params.VERSION}"
                
            }
        }
    }
}
