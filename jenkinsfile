pipeline {
    
    agent {
        label {
            label 'built-in'
            customWorkspace '/data/pipeline-1'
        }
    }
    
    stages {
        stage ('on-master'){
            steps {
                sh 'yum install tree -y'
            }
        }
        
        stage ('on-slave') {
            agent {
                label {
                    label 'slave1'
                    customWorkspace '/mnt/pipeline-1'
                }
            }
            steps {
                sh 'sudo yum install tree -y'
                sh 'sudo yum install git -y'
                sh 'sudo yum install httpd -y'
            }
        }
    }
}
