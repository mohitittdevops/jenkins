pipeline {
    agent any
    stages {
        stage('Pull and deploy image') {
            steps {
                sshagent(['13.232.193.60']) {
                   withDockerRegistry(credentialsId: 'ecr:ap-south-1:d6ff9dfc-6cda-4d1e-a8c8-c47b785e178b', url: 'https://265595627861.dkr.ecr.ap-south-1.amazonaws.com/php-image') {
                          //sh 'mkdir new-folder'
                          //sh 'ifconfig'
                        sh 'docker pull 265595627861.dkr.ecr.ap-south-1.amazonaws.com/php-image:new'
                        sh 'docker run -td -p 8100:80 265595627861.dkr.ecr.ap-south-1.amazonaws.com/php-image:new'
                    }
                }
            }
        }
    }
}