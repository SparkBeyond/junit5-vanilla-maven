pipeline {
    options {
        quietPeriod 0
        timestamps()
    }
    agent {
        label 'master'
    }
    stages {
        stage('Test') {
            steps {
                echo 'run test'
            }
            post {
                always {
                    junit 'build/test-results/**/*.xml'
                }
            }
        }
    }
}
