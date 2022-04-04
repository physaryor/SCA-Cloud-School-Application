
Skip to content

    Product 

Team
Enterprise
Explore
Marketplace
Pricing

Sign in
Sign up
Samuelseggs /
mvn-scp
Public

Code
Issues
Pull requests
Actions
Projects
Wiki
Security

    Insights

mvn-scp/Jenkinsfile
@Samuelseggs
Samuelseggs Done2
Latest commit b396992 20 hours ago
History
1 contributor
25 lines (24 sloc) 530 Bytes
pipeline {
  agent any
 
  tools {
  maven 'MAVEN3'
  }
  stages {
    stage ('Build') {
      steps {
      sh 'mvn clean install -f MyWebApp/pom.xml'
      }
    }
    stage ('JaCoCo') {
      steps {
      jacoco()
      }
    }
    stage ('Dev Deploy') {
      steps {
      echo "deploying to DEV Env "
      deploy adapters: [tomcat9(credentialsId: '7177fb7b-3b26-46b8-ae25-adaf5df8d1a5', path: '', url: 'http://ec2-18-117-167-234.us-east-2.compute.amazonaws.com:8080')], contextPath: null, war: '**/*.war'
      }
    } 
  }
}
