pipeline{
    agent any
    stages{
        stage ("cloning"){
            steps{
                git url: "https://github.com/gowtham123K/SECOND.git", branch: "main"
            }
        }
        stage ("dependency"){
            steps{
                bat '''
                   C:\\Users\\gowth\\AppData\\Local\\Programs\\Python\\Python313\\python.exe -m venv venv 
                   call venv\\Scripts\\activate
                   C:\\Users\\gowth\\AppData\\Local\\Programs\\Python\\Python313\\python.exe -m pip install --upgrade pip
                   pip install pytest
                '''   
            }
        }
        stage ("testing"){
            steps{
                bat '''
                    call venv\\Scripts\\activate
                    pytest test_calculater.py
                    '''
            }
        }
        stage ("deploy"){
            steps{
                bat '''
                call venv\\Scripts\\activate
                C:\\Users\\gowth\\AppData\\Local\\Programs\\Python\\Python313\\python.exe Calculater.py
                '''
            }
        }
    }
}
