
pipeline {
    agent {
        label 'UBUNTU'
    }

    stages {

        stage('Build Project') {
            steps {
                sh '''
                    echo "Build Spring PetClinic project"
                    mvn clean package
                '''
            }
        }

        stage('Run Application') {
            steps {
                sh '''
                    cd target
                    timeout 10m java -jar spring-petclinic-4.0.0-SNAPSHOT.jar
                '''
            }
        }
    }

    post {
        success {
            echo "Build and execution completed successfully"
        }
        failure {
            echo "Build failed"
        }
    }
}
