pipeline{
    agent any
    tools{
        jdk 'Java2'
        maven 'mymaven'
    }
    stages{
        stage("COMPILE"){
            steps{
                script{
                    echo "compiling the code"
                    sh 'mvn compile'
                }
            }
        }
        stage("UNITTEST"){
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
            steps{
                script{
                    echo "Packaging the code"
                    sh 'mvn package'
                }
            }
        }
        stage("DEPLOY"){
            steps{
                script{
                    echo "Deploying the app"
                }
            }
        }
    }
}
