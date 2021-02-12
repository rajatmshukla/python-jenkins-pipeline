node('master') {
    stage("Fetch Source Code") {
        git([url:'https://github.com/rajatmshukla/python-jenkins-pipeline',branch:'add-functions-and-tests'])
    }
    dir('.'){
        printMessage('running pipeline')
        stage("Testing") {
            bat 'python test_functions.py'
        }
        stage("Deployment") {
            if (env.BRANCH_NAME == 'master') {
                printMessage('Deploying the master branch')
            } else {
                printMessage("No deployment for branch [${env.BRANCH_NAME}]")
            }
        }
        }
        printMessage('Pipeline Complete')
    
}

def printMessage(message) {
    echo "${message}"
}
