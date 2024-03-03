pipeline {
    agent{
        label 'my_node-1'
    } 
    stages{
        stage ('git'){
            steps{
             sh 'sudo su -'   
             sh 'dnf install git -y'
             sh 'uname -a'     
            }
            
        }

        stage('git_version'){
            steps{
                sh '''
                git --version
                java --version
                '''
            }
        }
    }
post{
    always {
        echo 'this is run in node-1 instance'
    }
    success {
        echo 'the build was success..'
    }
    failure {
        echo 'the build was failure'
    }
}
 
}

