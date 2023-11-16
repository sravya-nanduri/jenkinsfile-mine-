pipeline{
    agent any
        stages{
            stage('git pull'){
                steps{
                git url: 'https://github.com/sravya-nanduri/rent-a-car.git', branch:'master'
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
                scp -r build/* user@13.232.48.199:/var/www/html


                '''
                }
            }
        }
}
