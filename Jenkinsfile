pipeline{
    agent{
        docker{
            image 'mcr.microsoft.com/playwright:v1.17.2-focal'
        }
    }
    stages{
        stage('Install playwright'){
            steps{
                sh '''
                    npm i -D @playwright/test
                    npx playwright install
                '''
            }
        }
        stage('help') {
            steps {
                sh '''
                    npx playwright show-report
                '''
            }
        }
        stage('test'){
            steps{
                sh '''
                    npx playwright test --list
                    npx playwright test
                '''
            }
        }
        // stage('repport') {
        //     steps {
        //         sh '''
        //             npx playwright show-report
        //         '''
        //     }
        // }
    }
}