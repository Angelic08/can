pipeline{
    agent any

    stages{
        stage("git clone"){
            steps{
                git url:'https://github.com/Angelic08/can.git', branch:'main'
            }
        }
        stage('install dependencies'){
            steps{
                bat '''
                C:\\Users\\hp\\AppData\\Local\\Programs\\Python\\Python312\\python.exe -m venv venv
                call venv\\Scripts\\activate
                pip install --upgrade pip
                pip install pytest
                '''
            }
        }

        stage('Run tests'){
            steps {
                bat '''
                call venv\\Scripts\\activate
                pytest test_num.py
                '''            
            }
        }

        stage('Deploy'){
            steps {
                echo 'Deploying application..'

                bat '''
                call venv\\Scripts\\activate
                C:\\Users\\hp\\AppData\\Local\\Programs\\Python\\Python312\\python.exe add_num.py
                '''
            }
        }
    }
}
