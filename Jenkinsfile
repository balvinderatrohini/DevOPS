pipeline {
    agent any

    stages {

        stage('Checkout from GitHub') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/balvinderatrohini/DevOPS.git'
            }
        }

        stage('Deploy to jboss servitium') {
            steps {
                sh '''
                    ansible-playbook -i ansible/inventory ansible/sample_war_deploy.yml -e "war_file=/home/Project/DevOPS/sample.war"
                '''
            }
        }
    }
}
