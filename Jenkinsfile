pipeline {
    agent any

    stages {
    stage('clone')
    {
    steps{
    git 'https://github.com/divineserpant/cal.git'
    }
    }
    
    stage('SCM') {
            steps {
                git url: 'https://github.com/divineserpant/cal.git'
            }
        }
        stage('SonarQube analysis') {
            steps {
                withSonarQubeEnv('sonar') {
                    
                     
                        bat 'mvn clean package sonar:sonar'
                    
                }
            }
        }

        stage('build')
        {
            steps{
                bat 'mvn clean compile'
                bat 'mvn clean install'
            }
        }
    }
}
