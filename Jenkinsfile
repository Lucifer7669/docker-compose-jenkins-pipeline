//this is httpd-deployment using dockerfile

pipeline {
   agent {
        node {
            label "built-in"
            customWorkspace "/srv"
        }

    }
    stages {
        stage ('dockerfile-building-phase-1') {
            steps {
            sh "cd docker-compose-jenkins-pipeline && docker-compose down"
            sh "docker system prune -a -f"
            sh "rm -rf *"
            sh "git clone https://github.com/Lucifer7669/docker-compose-jenkins-pipeline.git"
            sh "cd docker-compose-jenkins-pipeline && docker-compose up -d"
            sh "docker exec -it docker-compose-jenkins-pipeline-centos-httpd-1 bash && chmod 777 /var/www/html/"
            }
        
        }
    }
} 