node{
    def mvnhome=tool name:'Maven3.6.1', type:'maven'
    stage('Checkoutcode'){
    git credentialsId: '750978f8-fd56-4619-8238-9412b8368e97', url: 'https://github.com/puppala-bs/maven-web-application.git'
    }
    stage('Build'){
    sh "${mvnhome}/bin/mvn clean package"    
    } 
    stage('DeploytoTomcat')
    sshagent(['ae9c603a-7444-4982-af2e-ddf1ed61b89b']) {
    // some block
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.93.220.72:/opt/apache-tomcat-9.0.20/webapps/maven-web-application.war"
    }
}
