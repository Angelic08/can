pipeline{
    agent any

    stages{
        stage("git clone"){
            steps{
                url:'https://github.com/Angelic08/can.git', branch:'main'
            }
        }
        stage('install dependencies'){
            steps{
                bat '''
                python -m venv venv
                call venv\\Script\\activate
                pip install --upgrade pip
                pip install pytest
                '''
            }
        }

        stage('Run tests'){
            steps {
                bat '''
                call venv\\Scripts\\activate
                pytest test.py
                '''            
            }
        }

        stage('Deploy'){
            steps {
                echo 'Deploying application..'

                bat '''
                call venv\\Scripts\\activate
                python add.py
                '''
            }
        }
    }
}
