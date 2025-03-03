pipeline {
    agent any

    tools {
        maven 'm2'  
    }

    stages {
        stage('Checkout Code') {
            steps {
                ws('/mnt/Train-Ticket-Reservation-System') { 
                    git branch: 'master', url: 'https://github.com/CodeSwapnil-save/Train-Ticket-Reservation-System.git'
                }
            }
        }

        stage('Build with Maven') {
            steps {
                ws('/mnt/Train-Ticket-Reservation-System') {
                    sh 'mvn clean install'
                }
            }
        }

        stage('Run Tests') {
            steps {
                ws('/mnt/Train-Ticket-Reservation-System') {
                    sh 'mvn test'
                }
            }
        }

        stage('Package') {
            steps {
                ws('/mnt/Train-Ticket-Reservation-System') {
                    sh 'mvn package'
                }
            }
        }
    }
}
