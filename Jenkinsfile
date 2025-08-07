pipeline {

    agent any

    parameters {
        string (name: 'branch', defaultValue: 'main', description: 'some info')
    }

    stages {
        stage ("SCM") {
            steps {
                git branch:"${params.branch}", url: 'https://github.com/venkyscafe/Hello-Parallel.git'
            }
        }

        stage ("Static Analysis") {
            steps {
                echo "perform Static Analysis"
            }
        }

        stage ("Build") {
            steps {
                echo "build the code"
            }
        }

        stage ("Unit Test") {
            steps {
                echo "execute unit tests"
            }
        }

        stage ("Package") {
            steps {
                echo "Packaging the code for release"
            }
        }
    }
}