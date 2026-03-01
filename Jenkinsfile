pipeline {    
    agent any 
    tools {
        jdk 'jdk17'
        maven 'maven3'
    }

    stages {   
        stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }
        
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        
        stage('Build') {
            steps {
                sh 'mvn package'
            }
        }
    }
  post { 
    always { 
        script { 
            def jobName = env.JOB_NAME 
            def buildNumber = env.BUILD_NUMBER 
            def pipelineStatus = currentBuild.result ?: 'UNKNOWN' 
            def bannerColor = pipelineStatus.toUpperCase() == 'SUCCESS' ? 
'green' : 'red' 
 
            def body = """ 
                <html> 
                <body> 
                <div style="border: 4px solid ${bannerColor}; padding: 
10px;"> 
                <h2>${jobName} - Build ${buildNumber}</h2> 
                <div style="background-color: ${bannerColor}; padding: 
10px;"> 
                <h3 style="color: white;">Pipeline Status: 
${pipelineStatus.toUpperCase()}</h3> 
                </div> 
                <p>Check the <a href="${BUILD_URL}">console output</a>.</p> 
                </div> 
                </body> 
                </html> 
            """ 
 
            emailext ( 
                subject: "${jobName} - 
${pipelineStatus.toUpperCase()}", 
                body: body, 
                to: 'hanzala.coder@gmail.com', 
                from: 'jenkins@hanzala.com', 
                replyTo: 'jenkins@hanzala.com',  
                mimeType: 'text/html', 
                
            ) 
        } 
    } 
} 
}
