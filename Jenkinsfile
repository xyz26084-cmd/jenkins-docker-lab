pipeline {
    agent any 
    
    environment { 
        DOCKER_IMAGE = 'java-hello:v10' 
    } 
    
    stages { 
        stage('Docker Build') { 
            steps { 
                sh "docker build -t ${env.DOCKER_IMAGE} ." 
            } 
        } 
        stage('Docker Run') { 
            steps { 
                sh "docker run --rm ${env.DOCKER_IMAGE}" 
            } 
        } 
    } 
    
    post { 
        success { 
            echo 'Java image built successfully!' 
        } 
        failure { 
            echo 'An error occurred while building/running the image' 
        } 
    } 
}
