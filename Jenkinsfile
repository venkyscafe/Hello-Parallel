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

        stage ("Parallel Phase") {
                parallel {
                stage ("Static Analysis") {
                    steps {
                        echo "perform Static Analysis"
                        sleep time: 3, unit: 'SECONDS'
                    }
                }

                stage ("Build and Unit Test") {
                    stages {
                        stage ("Build") {
                            steps {
                                echo "build the code"
                                sleep time: 3, unit: 'SECONDS'
                            }
                        }

                        stage ("Unit Test") {
                            steps {
                                echo "execute unit tests"
                                sleep time: 3, unit: 'SECONDS'
                            }
                        }
                    }
                }
            } 
        }

        stage ("Package") {
            steps {
                echo "Packaging the code for release"
            }
        }
    }
}