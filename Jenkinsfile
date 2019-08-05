pipeline {
    agent any
    tools { 
        maven 'Maven 3.5.2' 
        jdk 'JDK 8' 
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }
        stage ('install') {
            steps {
                dir ('initial') {
                    sh 'mvn -Dmaven.test.failure.ignore=true install'
                } 
            }
        }
        stage ('Compile Stage') {
            steps {
                dir("initial"){
                    withMaven(maven : 'Maven 3.5.2') {
                        sh 'mvn clean install'
                    }
                }
            }
        }
        /*stage ('test') {
            steps {
                dir ('initial') {
                    sh 'mvn test'
                } 
            }
        }
        stage ('verify') {
            steps {
                dir ('initial') {
                    sh 'mvn verify'
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
        stage ('package') {
            steps {
                dir ('initial') {
                    sh 'mvn package'
                } 
            }
        }*/        
    }
}
