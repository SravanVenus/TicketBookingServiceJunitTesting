pipeline {
    agent any
    stages {
        stage('git repo & clean') {
            steps {
                bat "rmdir  /s /q TicketBookingServiceJunitTesting"
                bat "git clone https://github.com/kishancs2020/TicketBookingServiceJunitTesting.git"
                bat "clean -f TicketBookingServiceJunitTesting"
            }
        }
        stage('install') {
            steps {
                bat "install -f TicketBookingServiceJunitTesting"
            }
        }
        stage('test') {
            steps {
                bat "test -f TicketBookingServiceJunitTesting"
            }
        }
        stage('package') {
            steps {
                bat "package -f TicketBookingServiceJunitTesting"
            }
        }
    }
}
