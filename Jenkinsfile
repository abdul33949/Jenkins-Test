pipeline {
    agent any
    stages {
        stage('git repo & clean') {
            steps {
                sh "rm -rf TicketBookingServiceJunitTesting"
                sh "git clone https://github.com/abdul33949/Jenkins-Test.git"
                sh "mvn clean -f TicketBookingServiceJunitTesting"
            }
        }
        stage('install') {
            steps {
                sh "mvn install -f Jenkins-Test.git"
            }
        }
        stage('test') {
            steps {
                sh "mvn test -f Jenkins-Test.git"
            }
        }
        stage('package') {
            steps {
                bat "mvn package -f Jenkins-Test.git"
            }
        }
    }
}
