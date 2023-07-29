pipeline {

agent any

    stages{

            stage('clean the code ')
            {
                steps{
                    sh 'mvn clean'
                }
            }
            stage ('Unit Testing')
            {
                steps{
                sh 'mvn test'
                }
            }
    }
}