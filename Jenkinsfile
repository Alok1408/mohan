pipeline {
    agent any
    environment {
        name = 'alok'
    }
    parameters {
        string(name: 'Baby' , defaultValue: 'Monika', description: 'who are you?')
        choice(name: 'city', choices: ['gwl','delhi','Mumbai'] , description: '')
    }

    stages {
        stage('test') {
            steps {
                echo 'this is for test'
            }
        }
         stage('parameters') {
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
                sh 'echo "${Baby}"'
            }
        }
         stage('deploy in server') {
            input{
                 message "should we continue"
                 ok "yes you can"
             }
            steps {
                echo 'first deploy in server'
            }
        }
         stage('deploy in prod') {
            steps {
                echo 'deploy in production'
            }
        }
    }
    post {
        always {
            echo 'i am here always'
        }
    }
}
