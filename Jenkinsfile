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
            sh 'oc login --token= --server=https://api.sandbox.x8i5.p1.openshiftapps.com:6443'
          }
        }
        stage('new app') {
          steps {
            sh 'oc new-app https://github.com/himanshuchandan/node-hello --name=node-app3 --strategy=source'
          }
        }
        stage('logs') {
                steps {
                sh 'oc logs -f bc/node-app3'  
            }
        }
      stage('expose') {
          steps {
            sh 'oc expose svc/node-app3'
          }
        }
       stage('route') {
          steps {
            sh 'oc get route'
          }
        }
    }
}
