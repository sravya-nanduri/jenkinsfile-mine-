pipeline{
    agent any
        stages{
            stage('git pull'){
                steps{
                git url: 'https://github.com/sravya-nanduri/react-app.git', branch:'master'
                }
            }
            stage('building the app'){
             steps{
                sh '''
                sudo su -
                npm install
                npm run build
                '''
             }

            }
            stage('Copying the build file'){
                steps{
                sh '''
                sudo su -
                scp -v  build/* user@65.0.30.31:/var/www/html

                '''
                }
            }
        }
}
