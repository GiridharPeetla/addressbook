pipeline{
    agent none
    tools{
        jdk 'java2'
        maven 'mymaven'
    }
    stages{
        stage("COMPILE"){
            agent {label 'linux_slave'}
            steps{
                script{
                    echo "Compiling the code"
                    sh 'mvn compile'
                }
            }
        }
        stage("UNITTEST"){
            agent any
            steps{
                script{
                    echo "Testing the code"
                    sh 'mvn test'
                }
            }
            post{
                always{
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
         stage("PACKAGE"){
             agent {label 'linux_slave'}
            steps{
                script{
                    echo "Packaging the code"
                    sh 'mvn package'
                }
            }
        }
         stage("DEPLOY"){
            agent any
            steps{
                script{
                    echo "Deploying the app"
                }
            }
        }
    }
}
