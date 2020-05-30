node {
  //  stage('Run Test Scripts') {
  //    docker run -v ~/deploy/test:/etc/newman \
  //     --entrypoint /bin/sh postman/newman \
  //     -c "npm i -g newman-reporter-html;newman run DemoCollection.json -r html --reporter-html-export='newman-report.html'"
  //  }
   stage('Send Result File To Slack') {
     customWorkspace '/deploy/test'
     slackSend color: 'good', message: 'Message from Jenkins Pipeline'
   }
}