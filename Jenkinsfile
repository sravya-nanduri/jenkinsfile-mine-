pipeline{
    agent any
        stages{
            stage('git pull'){
                git url: 'https://github.com/sravya-nanduri/netflix.git', branch:'main'
            }
            stage('building the app'){
                sh '''
                sudo su -
                mkdir ~/new
                cd new
                apt update -y
                apt install nodejs -y
                apt install nvm -y
                nvm install n -y
                n 18.18.0
                npm install
                npm run build
                '''

            }
            stage('Copying the build file'){
                sh '''
                scp root@3.110.94.54:~/new/build/* user@65.0.30.31:/var/www/html
                '''
            }
        }
}