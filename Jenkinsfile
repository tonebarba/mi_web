pipeline {
    agent any

    stages {
        stage('Clonar repo') {
            steps {
                git 'https://github.com/tonebarba/mi_web.git'
            }
        }

        stage('Desplegar en Docker') {
            steps {
                // Copiamos archivos al volumen que monta Apache
                bat '''
                robocopy "%WORKSPACE%" "C:/Users/Usuario/mi_web" /MIR /FFT /Z /W:5
                if %ERRORLEVEL% LSS 8 exit 0
                exit %ERRORLEVEL%
                '''
            }
        }
    }

    post {
        success {
            echo "¡Despliegue completado!"
        }
        failure {
            echo "Error en el despliegue"
        }
    }
}