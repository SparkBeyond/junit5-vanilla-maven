pipeline {
    options {
        quietPeriod 0
        timestamps()
    }
    agent {
        kubernetes {
            yamlFile 'agent.yaml'
            defaultContainer('java')
        }
    }
    stages {
        stage('Test') {
            steps {
                sh './gradlew clean test'
            }
            post {
                always {
                    junit 'build/test-results/**/*.xml'
                }
            }
        }
    }
}
