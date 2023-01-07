pipeline {
//     agent {
//         docker {
//             image 'maven:3.8.7-eclipse-temurin-11'
// //             args '-v C:/Users/Alp/.m2:/root/.m2'
//         }
//     }
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                echo 'deliver stage'
            }
        }
    }
}