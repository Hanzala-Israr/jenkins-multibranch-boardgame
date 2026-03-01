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
                // Fallback to 'SUCCESS' if result is null (common in 'always' blocks)
                def pipelineStatus = currentBuild.result ?: 'SUCCESS' 
                def bannerColor = pipelineStatus == 'SUCCESS' ? 'green' : 'red' 
 
                def body = """ 
                    <html> 
                    <body> 
                    <div style="border: 4px solid ${bannerColor}; padding: 10px;"> 
                    <h2>${jobName} - Build ${buildNumber}</h2> 
                    <div style="background-color: ${bannerColor}; padding: 10px;"> 
                    <h3 style="color: white;">Pipeline Status: ${pipelineStatus}</h3> 
                    </div> 
                    <p>Check the <a href="${env.BUILD_URL}">console output</a>.</p> 
                    </div> 
                    </body> 
                    </html> 
                """ 
 
                emailext ( 
                    // FIX: Joined the subject onto one line
                    subject: "${jobName} - ${pipelineStatus}", 
                    body: body, 
                    to: 'hanzala.coder@gmail.com', 
                    from: 'jenkins@hanzala.com', 
                    replyTo: 'jenkins@hanzala.com',  
                    mimeType: 'text/html'
                ) 
            } 
        } 
    } 
}
