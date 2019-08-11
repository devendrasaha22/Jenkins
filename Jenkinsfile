node()
{
    stage "Checkout Code"
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/nvn17git/nvnshoppingcart']]])
    
    stage "Build Code"
        sh "mvn clean package"
        
    stage "Deploy Application"
        //sh 'rm /var/lib/tomcat/webapps/nvnshoppingcart*'
        //sh  'sudo cp **/*.war /opt'
        sh 'sudo cp /var/lib/jenkins/workspace/DemoPipeline/target/nvnshoppingcart.war /opt/apache-tomcat-8.0.23/webapps'
}
