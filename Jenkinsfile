pipeline {
agent any
    
tools {
    jdk 'JDK21'
    maven 'Maven3'
}

stages {
    stage('Checkout') {
        steps {
            checkout scm
        }
    }

    stage('Verify Tools') {
        steps {
            sh 'java -version'
            sh 'mvn -version'
        }
    }

    stage('Clean') {
        steps {
            sh 'mvn clean'
        }
    }

    stage('Compile') {
        steps {
            sh 'mvn compile'
        }
    }

    stage('Test') {
        steps {
            sh 'mvn test'
        }
    }

    stage('Package') {
        steps {
            sh 'mvn package -DskipTests'
        }
    }

    stage('Verify Artifact') {
        steps {
            sh 'ls -lh target/'
        }
    }
}

post {
    success {
        archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
    }

    always {
        cleanWs()
    }
}

}
