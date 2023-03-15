//poorna
pipeline {
    agent { label 'ubuntu' } 
        triggers { pollSCM ('* * * * *') }
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
        stage('post build') {
            steps {
                archiveArtifacts artifacts: '**/target/spring-petclinic-3.0.0-SNAPSHOT.jar',
                                 onlyIfSuccessful: true
                junit testResults: '**/surefire-reports/TEST-*.xml'
            }
        }
    }
} 