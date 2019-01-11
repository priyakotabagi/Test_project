pipeline {
    agent any 
    stages {
        stage('Clone repo and clean') { 
            steps {
                // bat "git clone https://github.com/priyakotabagi/Test_project"
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '0fb49048-df86-4a27-bdbd-d14f55c0773c', url: 'https://github.com/priyakotabagi/Test_project.git']]])
                
            }
        }
        stage('Test') { 
            steps {
                bat "mvn test -f ${env.workspace}\\testproject"
            
            }
        }
        stage('Deploy') { 
            steps {
                echo "Deployment stage"
            }
        }
    }
}
