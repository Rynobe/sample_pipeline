pipeline {
    environment {
        OTP_CDO_DATETIME = "${new Date().format("yyyyMMddHHmm")}"
    }
    options {
        timeout(time: 10, unit: "MINUTES")
        buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '20', daysToKeepStr: '', numToKeepStr: '20'))
        timestamps()
    }
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Rynobe/sample_pipeline.git']]])
            }
        }
        stage('Time') {
            steps{
                echo '${OTP_CDO_DATETIME}'
            }
        }
    }
}
