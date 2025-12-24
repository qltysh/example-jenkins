pipeline {
    agent any

    triggers {
        cron('0 0 * * *')  // Daily at midnight, same as GitHub Action schedule
    }

    environment {
        RUBY_VERSION = '3.1'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Setup Ruby') {
            steps {
                // Install Ruby using rbenv or rvm if available, or use a Ruby Docker image
                // This assumes Ruby is available on the Jenkins agent
                sh '''
                    ruby --version
                '''
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'bundle install --jobs 4 --retry 3'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'bundle exec rspec --require spec_helper'
            }
        }

        stage('Upload Coverage') {
            steps {
                sh '''
                    curl -sSL https://qlty.sh | sh
                    qlty coverage publish coverage/coverage.json
                '''
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
