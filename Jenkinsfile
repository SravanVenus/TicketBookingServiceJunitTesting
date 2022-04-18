pipeline {
    agent any
    tools { 
        maven 'maven_3.8.5' 
        jdk 'jdknew' 
    }
    stages {
        stage ('Initialize') {
            steps {
                bat '''
                    echo "PATH = ${PATH}"
                    echo "MAVEN_HOME = ${MAVEN_HOME}"
                ''' 
            }
        }

    stages {
        stage('git repo & clean') {
            steps {
                bat "rmdir  /s /q TicketBookingServiceJunitTesting"
                bat "git clone https://github.com/kishancs2020/TicketBookingServiceJunitTesting.git"
                bat "mvn clean -f TicketBookingServiceJunitTesting"
            }
        }
        stage('install') {
            steps {
                bat "mvn install -f TicketBookingServiceJunitTesting"
            }
        }
        stage('test') {
            steps {
                bat "mvn test -f TicketBookingServiceJunitTesting"
            }
        }
        stage('package') {
            steps {
                bat "mvn package -f TicketBookingServiceJunitTesting"
            }
        }
    }
}
