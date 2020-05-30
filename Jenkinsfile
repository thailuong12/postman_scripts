pipeline {
    agent any
    stages {
        stage('Run Test Collection') {
            steps {
                sh '''
                docker run --rm -v ~/deploy/test:/etc/newman \
                --entrypoint /bin/sh postman/newman \
                -c "npm i -g newman-reporter-html;newman run DemoCollection.json -r html --reporter-html-export=newman-report.html"
                '''
            }
        }
        stage('Send Result File') {

            // steps {
            //     withCredentials([string(credentialsId:'thai_slack', variable: 'SECRET')]) {
                    slackUploadFile channel: 'alert',
                              filePath: '~/deploy/test/newman-report.html',
                              tokenCredentialId: 'thai_slack',
                            //   baseUrl: 'https://hooks.slack.com/services'
            //         }
               
            // }
        }
    }
}