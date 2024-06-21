pipeline{
    agent { label 'aws' }
    environment{
        TOKENAWS = credentials('aws-cr')
    }
    stages{ 
        stage('Deploy to Testing'){
            steps{
            sh 'ssh -T -oStrictHostKeyChecking=no -i "$TOKENAWS" ec2-user@54.160.29.83 " sudo dnf update; sudo dnf install git -y; sudo dnf install -y httpd; sudo systemctl start httpd; sudo rm -Rf /var/www/html/; sudo git clone https://github.com/eduval/TrainingExercise /var/www/html"'
            }
        }
        stage('Deploy to Staging'){
            steps{
            sh 'ssh -T -oStrictHostKeyChecking=no -i "$TOKENAWS" ec2-user@3.239.223.239 " sudo dnf update; sudo dnf install git -y; sudo dnf install -y httpd; sudo systemctl start httpd; sudo rm -Rf /var/www/html/; sudo git clone https://github.com/eduval/TrainingExercise /var/www/html"'
            }
        }
        stage('Deploy to Production_Env1'){
            steps{
            sh 'ssh -T -oStrictHostKeyChecking=no -i "$TOKENAWS" ec2-user@52.202.243.240 " sudo dnf update; sudo dnf install git -y; sudo dnf install -y httpd; sudo systemctl start httpd; sudo rm -Rf /var/www/html/; sudo git clone https://github.com/eduval/TrainingExercise /var/www/html"'
            }
        }
        stage('Deploy to Production_Env2'){
            steps{
            sh 'ssh -T -oStrictHostKeyChecking=no -i "$TOKENAWS" ec2-user@44.220.93.150 " sudo dnf update; sudo dnf install git -y; sudo dnf install -y httpd; sudo systemctl start httpd; sudo rm -Rf /var/www/html/; sudo git clone https://github.com/eduval/TrainingExercise /var/www/html"'
            }
        }
    }
}
