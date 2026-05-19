pipeline {
    agent any

    stages {
        stage('Disk Usage') {
            steps {
                script {
                    sh '''
                        echo "=== disc information ==="
                        df -h
                    '''
                }
            }
        }
        stage('Top Memory Process') {
            steps {
                script {
                    sh '''
                        echo "=== The process with maximum memory usage ==="
                        ps aux --sort=-%mem | awk 'NR==2 {print $11}'
                    '''
                }
            }
        }
    }

    post {
        always {
            sh 'echo "Monitoring finished"'
        }
    }
}
