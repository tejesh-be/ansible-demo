pipeline{
    agent { label 'ansible'}
    stages {
        stage('SCM Checkout') {
            steps {
                git 'https://github.com/tejesh-be/maven-helloworld.git'
            }
        }

        stage('Execute Ansible') {
            steps {
                ansiblePlaybook credentialsId: 'ansible_master', disableHostKeyChecking: true, installation: 'Ansible', inventory: 'tomcat.ini', playbook: 'install-tomcat.yaml'
            }
        }
    }
}