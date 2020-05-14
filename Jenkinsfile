node{
   stage('SCM Checkout'){

    git'https://github.com/Arun8055643220/hellow-world'
   }
   stage('Complie-package') {
       def mvnHome = tool name: 'mvn', type: 'maven'
   sh "=${mvnHome}/bin/mvn package"

}
stage ('Deploy to tomcat'){
sshagent(['tomcat']) {
    sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/target/*.war ec2-user@172.31.91.240:/opt/tomcat/apache-tomcat-9.0.34/webapps/'
}

}
