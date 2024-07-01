pipeline {
    agent any
    tools {
        maven "maven"
        jdk "openjdk-11"
    }
    environment {
        PASS = credentials('nexus')
        SNAP_REPO = 'vproflie-snapshot'
        NEXUS_USER = 'admin'
        RELEASE_REPO = 'vprofile-release'
        CENTRAL_REPO = 'vprofile-maven-central'
        NEXUS_URL = 'http://192.168.1.34:8081/'
        NEXUSPORT = '8081'
        NEXUS_GRP_REPO = 'vprofile-maven-group'

        // SNAP_REPO = 'vprofile-snapshot'
        // NEXUS_USER = 'admin'
        // NEXUS_PASS = 'admin123'
        // RELEASE_REPO = 'vprofile-release'
        // CENTRAL_REPO = 'vprofile-maven-central'
        // NEXUS_GRP_REPO = 'vprofile-maven-group'
        // NEXUS_LOGIN = 'nexuslogin'
        // NEXUSIP = 'http://192.168.1.34:8081/'
        // NEXUSPORT = '8081'

    }
    
    stages {
        stage ('CheckOut') {
            steps {
                git url: 'git@github.com:vanthiyadhevan/vprofile-project.git', branch: 'ci-jenkins', credentialsId:('vanthiyadhevan')
            }
        }
        stage('Build') {
            steps {
                sh 'mvn -s settings.xml -DskipTests'
            }
        }
    }
}