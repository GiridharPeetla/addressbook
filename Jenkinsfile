pipeline{
    agent any
    tool{
        jdk 'jav2'
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
