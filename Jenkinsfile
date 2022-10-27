pipeline {
    agent any
  
    stages {
        stage('checkprod') {
            steps {
                sh 'systemctl status apache2'
            }
        }
        stage('checktest') {
            steps {
                sh 'systemctl status tomcat9'
            }
        }
   
        stage('production') {
            when {
                branch 'main'
            }
            steps {
                sh 'cp **/* /var/lib/tomcat9/webapps/myapp/'
            }
        }
        stage('Testing-branch') {
            when {
                branch 'branch1'
            }
            steps {
                sh 'cp **/* /var/lib/www/'
            }
        }
    }
}
