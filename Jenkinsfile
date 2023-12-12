
pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/haseebhassan512/XYZ.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying..'
                sshPublisher(
                    publishers: [
                        sshPublisherDesc(
                            configName: 'HaseebINC',
                            transfers: [sshTransfer(sourceFiles: '**/*', remoteDirectory: '/haseeb')],
                        )
                    ]
                )
            }
        }
    }
}
