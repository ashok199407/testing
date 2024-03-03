pipeline {
    agent{
        label 'my_node-1'
    } 
    stages{
        stage('SCANNING'){
            steps{
                sh 'sudo su'
                sh 'cd /home/centos/workspace/djngo-api-deploy/hrms-complete'
                sh 'ls -ltr'
                sh 'sonar-scanner'
            }
        }
    }
post{
    always {
        echo 'this is run in node-1 instance'
    }
    success {
        echo 'the scanning was success..'
    }
    failure {
        echo 'the scanning was failure'
    }
}
 
}

