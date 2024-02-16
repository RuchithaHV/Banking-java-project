pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https:https://github.com/RuchithaHV/Banking-java-project/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with ruchitha'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with ruchitha'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with ruchitha'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with ruchitha'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c000 newimage1'
            }
        }   
    }
}
