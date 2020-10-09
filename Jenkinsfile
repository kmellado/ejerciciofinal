pipeline {

    agent any
    stages {

        stage('Build') {
            steps {
                sh '''
                        echo build 
			./jenkins/build/mvn.sh mvn -B -DskipTests clean package
			./jenkins/build/build.sh
			echo fin-buil
			echo fin-build
                    '''   
            }
        }                        
        stage('Test') {
            steps {
                               sh './jenkins/test/test.sh mvn test' 
            }
        }
        stage('Push') {
            steps {
                               sh './jenkins/test/push.sh'
            }
        }
        stage('Deploy') {
            steps {
                               sh 'echo deploy'
            }
        }
    }
}
