node {
  stage ('OWASP Dependency-Check Vulnerabilities') {  
    steps {  
     withMaven(maven : 'maven') {  
      sh 'mvn dependency-check:check'  
     }
     dependencyCheckPublisher pattern: 'target/dependency-check-report.xml'  
    }  
  } 
}
