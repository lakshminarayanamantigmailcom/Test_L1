pipeline {
    agent {label 'JDK'}
    parameters {
        choice(name: 'BRANCH', choices: ['main', 'lucky', 'luckyNode1'], description: 'select your branch')
        choice(name: 'BUILD', choices: ['package', 'install', 'clean install', 'clear sheat'], description: 'select your task')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/spring-projects/spring-petclinic.git',
                branch: "${prams.BRANCH}"
            }
        }
        stage('build') {
            steps {
                sh "${prams.BUILD}"
            }
        }
    }
}