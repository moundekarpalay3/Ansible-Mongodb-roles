pipeline {
    agent any 
    stages {
      stage('SCM Checkout') {
        steps {
           checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/moundekarpalay3/Ansible-Mongodb-roles.git']]])  
        }
      }  
      stage('Execute Ansible') {
        steps {
           ansiblePlaybook credentialsId: 'ansible', disableHostKeyChecking: true, installation: 'ansible-copsc', inventory: 'hosts', playbook: 'mongo-db.yaml'
        }  
      }
    }
}
