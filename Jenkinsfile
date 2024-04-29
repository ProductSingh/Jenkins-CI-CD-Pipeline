pipeline {
    agent any
    stages {
        // ... other stages ...

        stage('Unit and Integration Tests') {
            steps {
                // ... test commands ...
            }
            post {
                success {
                    emailext(
                        to: 'mankaran89@gmail.com',
                        subject: "SUCCESS: Integration Tests Passed - ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                        body: """<p>Good news, the integration tests passed!</p>
                                 <p>Check out the logs attached for more details.</p>""",
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        to: 'mankaran89@gmail.com',
                        subject: "FAILURE: Integration Tests Failed - ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                        body: """<p>Uh oh, the integration tests failed.</p>
                                 <p>See the attached logs for debugging.</p>""",
                        attachLog: true
                    )
                }
            }
        }

        // ... other stages ...

        stage('Security Scan') {
            steps {
                // ... security scan commands ...
            }
            post {
                success {
                    emailext(
                        to: 'mankaran89@gmail.com',
                        subject: "SUCCESS: Security Scan Passed - ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                        body: """<p>Great, the security scan passed!</p>
                                 <p>Attached are the logs for your review.</p>""",
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        to: 'mankaran89@gmail.com',
                        subject: "FAILURE: Security Scan Failed - ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                        body: """<p>Alert: The security scan has failed.</p>
                                 <p>Please review the attached logs.</p>""",
                        attachLog: true
                    )
                }
            }
        }
    }
}


