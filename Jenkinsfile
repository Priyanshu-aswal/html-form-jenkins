
pipeline {
    agent any

    stages {
       stage('Checkout') {
    steps {
        git branch: 'main',
            url: 'https://github.com/Priyanshu-aswal/html-form-jenkins.git'
    }
}

        stage('Test HTML Form') {
            steps {
                script {
                    def html = readFile('index.html')

                    if (!html.contains('<form')) {
                        error('FAIL: Form not found')
                    }

                    if (!html.contains('id="name"')) {
                        error('FAIL: Name field not found')
                    }

                    if (!html.contains('id="email"')) {
                        error('FAIL: Email field not found')
                    }

                    if (!html.contains('id="contact"')) {
                        error('FAIL: Contact field not found')
                    }

                    if (!html.contains('type="submit"')) {
                        error('FAIL: Submit button not found')
                    }

                    echo 'PASS: HTML form and all required fields found!'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check the console output.'
        }
    }
}
