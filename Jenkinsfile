pipelineJob('docker-build-and-run') {
    definition {
        cps {
            script('''
pipeline {
    agent any

    stages {
        stage('Verify Docker Installation') {
            steps {
                echo 'Verificando si Docker está instalado y accesible...'
                sh 'docker --version'
            }
        }

        stage('Checkout') {
            steps {
                echo 'Clonando el repositorio desde GitHub...'
                git branch: 'main', url: 'https://github.com/dfloresc16/eurekams.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Construyendo la imagen Docker usando el DockerFile...'
                sh 'ls -al /var/jenkins_home/workspace/eurekams'
                sh 'docker build -t eurekams /var/jenkins_home/workspace/eurekams -f /var/jenkins_home/workspace/eurekams/DockerFile'
            }
        }

        stage('Run Docker Container') {
            steps {
                echo 'Ejecutando el contenedor Docker...'
                sh 'docker run -d --name eurekams-container -p 8761:8761 eurekams'
            }
        }

        stage('Verify Docker Container') {
            steps {
                echo 'Verificando el estado del contenedor...'
                sh 'docker ps -a'
                echo 'Mostrando los logs del contenedor...'
                sh 'docker logs eurekams-container'
            }
        }
    }

    post {
        always {
            echo 'Limpiando: Deteniendo y eliminando el contenedor...'
            sh 'docker stop eurekams-container || true'
            sh 'docker rm eurekams-container || true'
        }
    }
}
''')
        }
    }
}
