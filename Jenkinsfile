pipeline {
    agent any

    parameters {
        choice(
            name: 'jenkins_build_branch',
            choices: ['branch-1', 'branch-2'],
            description: 'Select Git Branch to Build'
        )
    }

    stages {

        stage('Clone Selected Branch') {
            steps {
                git branch: "${params.jenkins_build_branch}",
                    url: 'https://github.com/afnantypical/jenkins-built-with-parameters.git'
            }
        }

        stage('Run app.py') {
            steps {
                sh 'python3 app.py'
            }
        }
    }
}
