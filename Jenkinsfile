pipeline {
    agent {
        label 'jen-agent'
    }
    stages {
        stage('Preparation') {
            steps{
                git branch: 'main', url: 'https://github.com/exesition/vector-role.git'
            }
        }
        stage('Install requirements') {
            steps{
                sh 'pip3 install -r requirements.txt'
	        }
        }
        stage('Molecule test'){
            steps{
                sh 'molecule test'
                cleanWs()
            }
        }
    }
}
