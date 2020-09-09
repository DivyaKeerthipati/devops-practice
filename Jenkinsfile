pipeline
{
    agent any
    stages{
        stage('Checkout')
        {
            steps
            {
                git 'https://github.com/DivyaKeerthipati/DevOpsPracticeCode'
            }
        }
        stage('Compile')
        {
            steps
            {
                sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/myMaven/bin/mvn compile'
            }
        }
        stage('test')
        {
            steps
            {
                sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/myMaven/bin/mvn test'
            }
        }
        stage('package')
        {
            steps
            {
                sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/myMaven/bin/mvn package'
            }
        }
        stage('deploy')
        {
            steps
            {
                sh 'sudo cp /var/lib/jenkins/workspace/AddressBookPackage/target/addressbook.war /opt/tomcat/webapps'
                sh 'sudo systemctl stop tomcat'
                sh 'sudo systemctl start tomcat'
            }
        }
    }
}
