pipeline {
    agent any

    stages {
        stage('Clone the SCM Data') {
            steps {
                // checkout scm
                sh """
                    git clone https://github.com/aromaljosephkm/project_1.git
                """
            }
        }

        // stage('Execute ansible playbook') {
        //     steps {
        //         sh """
        //             ansible-playbook ansible.yaml
        //         """
        //     }
        // }

        stage('Docker image creation') {
            steps {
                sh """
                    docker build -f Dockerfile -t website:1 .
                """
            }
        }

        stage('Docker container service starting') {
            steps {
                sh """
                    docker run -d --name mywebsite5 website:1
                """
            }
        }
    }
}