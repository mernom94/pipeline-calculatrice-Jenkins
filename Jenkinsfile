pipeline {
    agent none

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'python:3.8-alpine3.16'
                    args '-u root'  // optional, if you need root access in container
                }
            }
            steps {
                sh 'python3.8 -m py_compile sources/prog.py sources/calc.py'
                stash(name: 'compiled-results', includes: 'sources/*.py*')
            }
        }
    }
}
