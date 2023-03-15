//poorna
pipeline {
    agent { label 'ubuntu' }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/purna970/spc-repo.git',
                    branch: 'sprint_1_release'
            }
        }
        stage('package') {
            steps {
                sh 'mvn package'
            }
        } 
       
    }
} 