pipeline {
    agent any

    stages {
        stage('Checkout')
        {

           steps {
                   checkout scm
                }
        }

        stage('Build')
        {
            steps {
                    dir('java-standalone-application'){
                    bat 'mvn -B clean install'
                    }

                 }
        }

        stage('Test')
        {
           steps {
                    dir('java-standalone-application'){
                       bat 'mvn -B test'
                   }
                }
        }

        stage('Publish Test Results')
        {
             steps {
                       junit 'java-standalone-application/target/surefire-reports/*.xml'
                    }
        }
    }
}
