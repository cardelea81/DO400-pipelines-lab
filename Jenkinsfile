pipeline {
    agent any

    stages {
        stage('Test') {

        }
    }
}

pipeline {
    agent any

    stages {
        stage('Test') {
            parallel {

            }
        }
    }
}



pipeline {
    agent any

    stages {
        stage('Test') {
            parallel {
                stage('Unit tests') {
                    steps {
                        sh './mvnw test -D testGroups=unit'
                    }
                }
            }
        }
    }
}



pipeline {
    agent any

    parameters {
        booleanParam(name: "RUN_INTEGRATION_TESTS", defaultValue: true)
    }

    stages {
        stage('Test') {
            parallel {
                ...output omitted...

                stage('Integration tests') {
                    when {
                        expression { return params.RUN_INTEGRATION_TESTS }
                    }

                    steps {
                        sh './mvnw test -D testGroups=integration'
                    }
                }
            }
        }
    }
}
