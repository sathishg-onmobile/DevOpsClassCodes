pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "Mymaven"
        jdk "MyJava"
    }

    stages {
        stage('Build') {
            steps {
              git 'https://github.com/devops-trainer/DevOpsClassCodes.git'
            }
        }
         stage('Compile') {
            steps {
              sh 'mvn compile'
            }
        }
         stage('CodeReview') {
            steps {
              sh 'mvn pmd:pmd'
            }
        }
         stage('Unit test') {
            steps {
              sh 'mvn test'
            }
        }
         stage('MetricTEST') {
            steps {
              sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
            }
        }
        stage('package') {
            steps {
              sh 'mvn package'
            }
        }
    }
}
