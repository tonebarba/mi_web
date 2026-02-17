pipeline {
 agent any
 stages {
 stage('Desplegar en Docker') {
 steps {
 echo "El código ya está en el workspace"
 sh 'ls -la'
 }
 }
 }
 post {
 success {
 echo "¡Pipeline ejecutado correctamente!"
 }
 failure {
 echo "Error en el pipeline"
 }
 }
}