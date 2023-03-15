pipeline{
    agent any
    environment 
    {     
    DOCKERHUB_CREDENTIALS= credentials('dockerhubcredentials')     
    } 
    
    stages{
        stage('git clone'){
            steps{
            sh 'git clone https://github.com/DPATEL2235/docker_jenkins.git'
        }
        }
        stage('Build an image'){
            steps{
                sh 'docker build -t dhrumil2235/ubuntu_pwd .'
       
            }
            }

        stage('Login'){ 
            steps{
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | sudo docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'                		
	            echo 'Login Completed'                     
            }       
        }

        stage('List'){
            steps{
                echo "docker"
                sh 'docker ps'
            }
        }
    }
    
}