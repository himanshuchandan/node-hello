pipeline{
    agent any
    tools{
        nodejs 'nodejs'
    }
    stages{
        
        stage('install') {
          steps {
            sh 'npm install'
          }
        }
        stage('login') {
          steps {
            sh ''
          }
        }
        stage('new app') {
          steps {
            sh 'oc new-app https://github.com/himanshuchandan/node-hello --name=node-app2 --strategy=source'
          }
        }
        stage('logs') {
                steps {
                sh 'oc logs -f bc/node-app'  
            }
        }
      stage('expose') {
          steps {
            sh 'oc expose svc/node-app'
          }
        }
       stage('route') {
          steps {
            sh 'oc get route'
          }
        }
    }
}
