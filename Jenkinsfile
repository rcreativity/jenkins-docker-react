stage 'Building'
node {

    checkout scm

    sh 'npm install'

    
          
}



//parallel integration testing
stage 'Testing'


node {
sh 'npm test -- --coverage'
notify("Deploy to staging?")
input 'Deploy to staging?'
}



// limit concurrency so we don't perform simultaneous deploys
// and if multiple pipelines are executing, 
// newest is only that will be allowed through, rest will be canceled
stage name: 'Deploy to staging', concurrency: 1
node {
    //sh 'https://github.com/rcreativity/jenkins-docker-react.git'
   // sh 'npm install'''
   
    git branch: 'master', 
        url:  'https://github.com/rcreativity/jenkins-docker-react.git'
        sh 'npm install'
        sh 'npm run-script build'
        notify 'Mental_shortcuts version 02 test webhook Deployed successfully!'
    
}
