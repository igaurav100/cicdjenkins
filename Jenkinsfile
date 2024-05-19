pipeline {
    agent any
    tools {
        tool name: 'maven', type: 'maven'
    }

    stages {
        stage ('Build') {
            sh 'mvn clean package'
        }

        stage ('Deploy') {
            deploy adapters: [tomcat9(credentialsId: 'd4482cf8-475c-4f9b-b02e-edb4a07f7459', 
            path: '', 
            url: 'http://192.168.152.133:8080')], 
            contextPath: null, 
            war: '**/*.war'
        }
    }
}