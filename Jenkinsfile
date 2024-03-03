pipeline {
    agent{
        label 'my_node-1'
    } 
    stages{
        stage ('git cloning'){
            steps{
             sh '''
             sudo su -   
             cd /home/centos/workspace/djngo-api-deploy/    
             cat << EOF | sudo tee sonar-project.properties
             sonar.projectkey=hrms
             EOF 
             ''' 
            }
            
        }

        stage('SCANNING'){
            steps{
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

