pipeline {
    agent any
    tools { 
        maven 'Maven 3.5.2' 
        jdk 'JDK 8' 
    }
    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'Maven 3.5.2') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'Maven 3.5.2') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'Maven 3.5.2') {
                    sh 'mvn deploy'
                }
            }
        }
    }
}
