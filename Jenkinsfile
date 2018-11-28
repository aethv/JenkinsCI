node {
    checkout scm
    env.PATH = "${tool 'Maven3'}/bin:${env.PATH}"

    stage('Build') {
        steps {
            sh 'mvn -B -DskipTests clean package'
        }
    }
    stage('Test') { 
        steps {
            sh 'mvn test' 
        }
        post {
            always {
                junit 'target/surefire-reports/*.xml' 
            }
        }
    }
}