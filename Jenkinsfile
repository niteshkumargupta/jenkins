pipeline
{
    agent any
       stages{
           stage('cloning') {
            steps {
                git credentialsId: 'Git', url: 'https://github.com/niteshkumargupta/jenkins.git'
            }
        }
        stage('Clone/Customization') {
            steps {
                echo 'Cloning....'
            }
        }
        stage('Patching') {
            steps {
                ansiblePlaybook become: true, credentialsId: 'patch', disableHostKeyChecking: true, installation: 'ansible 2.4.2.0', inventory: 'inventory.ini',limit: 'ubuntu', playbook: 'patch.yml'

            }
        }
        
    }
}
