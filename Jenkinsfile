pipeline{
    agent any
    
    tools{
        maven  'maven-3' 
        
    }
    
    
stages{
    stage('SCM Checkout'){

steps{
        
        git 'https://github.com/spandanasalian/Autodeploywebapp.git'
        }
    }
    
    stage('Compile Package'){
        steps{
            
            bat "mvn -Dmaven.test.failure.ignore=true clean package"
            

}

    }
    
     
    stage('Deploy'){
        steps{
            
           deploy adapters: [tomcat7(credentialsId: 'a87d9aca-3197-457a-bfa3-af28dcb9c039', path: '', url: 'http://localhost:8080')], contextPath: 'mvn-hello-world', onFailure: false, war: 'target/mvn-hello-world.war'

}


        
    }

}




}


