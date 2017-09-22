/**
 * A map of parallel runs built dynamically in the job. It is a map of closures
 */
def parallelCodeMap = [:]

/**
 * Declarative pipeline
 */
pipeline {

    agent any

    stages {

        stage('Setup') {

            steps {

                // Set up the dynamic parallel code map
                script {

                    parallelCodeMap['foo'] = {
                        echo "Running foo branch.."
                    }

                    parallelCodeMap['bar'] = {
                        echo "Running bar branch..."
                    }
                }
            }
        }

        stage('Dynamic') {
            steps {
                script {
                    parallel( parallelCodeMap )
                }
            }
        }

        stage('Static') {
            steps {
                parallel (
                    'branch_1' : {
                        echo "Running static branch 1"
                    },
                    'branch_2' : {
                        echo "Running static branch 2"
                    },
                )
            }
        }

    }
}
