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

            stage('Deploy on Tomcat')
            {
            steps{
              sh 'mvn package'
              sshagent(['tomcat']) {
                // some block
                sh """
                scp -o StrictHostKeyChecking=no **/*.war ec2-user@ip-172-31-20-183:/opt/tomcat/apache-tomcat-9.0.33/webapps
                """
                }
            }
            }
    }
}